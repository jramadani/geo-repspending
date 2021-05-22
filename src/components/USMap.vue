<template>
  <div id="map-container"></div>
  <div class="legendwrapper"><div class="legend"></div></div>
</template>
<script>
import * as d3 from "d3";
import "mapbox-gl/dist/mapbox-gl.css";
import mapboxgl from "mapbox-gl";

const height = window.innerHeight;

export default {
  name: "USMap",
  props: ["stepcatch", "spendata", "categories", "maindata"],
  data() {
    return {
      distmap: {},
      colorcode: [],
      legendcol: [],
      dist: null,
      selectedRep: null,
      selectedCategory: null,
    };
  },
  watch: {
    maindata(val, oldVal) {
      console.log("here's the old value!", oldVal);
      if (val != undefined) {
        this.colorcode = [];
        this.colorcode = this.geoidColor(val);
      }
    },
    colorcode(val, oldVal) {
      console.log("here's the old value!", oldVal);
      if (val.length > 0) {
        this.sourceLayer(val);
        this.mapColorUpdate();
        this.legend();
      } else {
        this.sourceLayer("rgba(0,0,0,0.1)");
      }
    },
  },
  methods: {
    showMap: function () {
      const mapcont = d3.select("#map-container");
      mapcont.attr("height", height * 0.9);
      mapboxgl.accessToken =
        "pk.eyJ1IjoianJhbWFkYW5pIiwiYSI6ImNrOW9xbWtmMzAxczYzZnA4bGlib2s3ZGgifQ.ZNLlxgGb_C51ZEzEGoPfbg";
      this.distmap = new mapboxgl.Map({
        container: "map-container",
        style: "mapbox://styles/jramadani/ckorze9cn473w17qtztugvpgf", // stylesheet location
        center: [-90, 40], // starting position [lng, lat]
        zoom: 4,
      });
      console.log("zip interior check", this.distmap);
    },
    sourceLayer: function () {
      this.distmap.on("load", () => {
        this.distmap.addSource("tl_2020_us_cd116-2rtrvr", {
          type: "vector",
          url: "mapbox://jramadani.91973db5",
        });
        this.distmap.addLayer({
          id: "mainmap",
          type: "fill",
          source: "tl_2020_us_cd116-2rtrvr",
          "source-layer": "tl_2020_us_cd116-2rtrvr",
          paint: {
            "fill-outline-color": "rgba(0,0,0,0.1)",
            "fill-color": "rgba(0,0,0,0.1)",
          },
        });

        this.mapColorUpdate();
      });

      this.distmap.on("click", "mainmap", (e) => {
        const format = d3.format(",." + d3.precisionFixed(1) + "f");
        this.distmap.getCanvas().style.cursor = "pointer";
        const feature = e.features[0];
        this.dist = feature.properties.GEOID;
        if (this.maindata != undefined && this.maindata.length > 0) {
          this.selectedRep = this.maindata.filter((d) => d.geoid == this.dist);
          console.log(this.selectedRep[0]);
          new mapboxgl.Popup()
            .setLngLat(e.lngLat)
            .setHTML(
              `
        <p><b>Representative:</b> ${this.selectedRep[0].fullname}</p>
        <p><b>Party:</b> ${this.selectedRep[0].party}</p>
        <p><b>Amount Spent:</b> ${format(this.selectedRep[0].amount)}</p>
        `
            )
            .addTo(this.distmap);
        } else {
          new mapboxgl.Popup()
            .setLngLat(e.lngLat)
            .setHTML(
              `<p>Please continue scrolling down the story to see information about this district!</p>`
            )
            .addTo(this.distmap);
        }
      });
    },

    geoidColor: function (datavalue) {
      //GEOID VERSION
      this.colorcode = [];
      let color = d3
        .scaleOrdinal()
        .domain([0, d3.max(datavalue, (d) => d.amount)])
        .range(
          [
            "#0d9ca2",
            "#49a9ab",
            "#70b5b5",
            "#8fc1c0",
            "#abcdcb",
            "#c4dad8",
            "#dae7e5",
          ].reverse()
        );
      let cc = [];
      const intersperse = datavalue.reduce((acc, property) => {
        const geo = `${property.geoid}`;
        acc[geo] = color(property.amount);
        return acc;
      }, {});
      const ia = Object.entries(intersperse);
      let flattening = ia.flat();
      flattening.unshift("match", ["get", "GEOID"]);
      flattening.push("rgba(0,0,0,0)");

      flattening.forEach((d) => {
        if (d == "rgb(0, 0, 0)") {
          cc.push("rgb(50, 7, 118)");
        } else {
          cc.push(d);
        }
      });
      return cc;
    },
    mapColorUpdate: function () {
      if (this.distmap.getLayer("selected-spending")) {
        this.distmap.removeLayer("selected-spending");
      }
      console.log(this.distmap);
      //  MAP -- REDRAWN WITH COLOR LAYERS
      console.log("what do the colors look like", this.colorcode);
      if (this.colorcode.length > 0) {
        this.distmap.addLayer({
          id: "selected-spending",
          source: "tl_2020_us_cd116-2rtrvr",
          "source-layer": "tl_2020_us_cd116-2rtrvr",
          type: "fill",
          paint: {
            "fill-color": this.colorcode,
            "fill-opacity": 0.8,
          },
        });
      } else {
        this.distmap.addLayer({
          id: "selected-spending",
          source: "tl_2020_us_cd116-2rtrvr",
          "source-layer": "tl_2020_us_cd116-2rtrvr",
          type: "fill",
          paint: {
            "fill-color": "rgba(0,0,0,0.1)",
            "fill-opacity": 0.8,
          },
        });
      }
    },
    legendConstruction: function (color, n = 256) {
      const canv = document.createElement("canvas");
      canv.width = n;
      canv.height = 1;
      const canvas = canv.getContext("2d");
      for (let i = 0; i < n; ++i) {
        canvas.fillStyle = color(i / (n - 1));
        canvas.fillRect(i, 0, 1, 1);
      }
      return canv;
    },
    legend: function () {
      //note to self to wrap this in an if statement
      //the arrays won't be loaded in yet
      if (this.maindata == undefined) {
        this.legendcol = [0, 3000000];
      } else {
        this.legendcol = d3
          .extent(this.maindata, (d) => d.amount)
          .map((d) => Math.floor(d));
        console.log("testing if this works??", this.legendcol);
      }

      if (this.maindata != undefined && this.maindata.length > 0) {
        d3.select(".legend svg").remove();
        //code base from Mike Bostock on Observable
        let legendColor,
          title,
          tickSize = 6,
          width = 320,
          height = 50 + tickSize,
          marginTop = 18,
          marginRight = 0,
          marginBottom = 16 + tickSize,
          marginLeft = 0,
          ticks = width / 64,
          tickFormat,
          tickValues;

        legendColor = d3.scaleSequential(this.legendcol, [
          "#dae7e5",
          "#0d9ca2",
        ]);

        title = "Amount Spent by Representative (USD)";

        const legendSvg = d3
          .selectAll(".legend")
          .append("svg")
          .attr("width", width)
          .attr("height", height)
          .attr("viewBox", [0, 0, width, height])
          .style("overflow", "visible")
          .style("display", "block");

        let tickAdjust = (g) =>
          g
            .selectAll(".tick line")
            .attr("y1", marginTop + marginBottom - height);
        let x;

        x = Object.assign(
          legendColor
            .copy()
            .interpolator(d3.interpolateRound(marginLeft, width - marginRight)),
          {
            range() {
              return [marginLeft, width - marginRight];
            },
          }
        );

        legendSvg
          .append("image")
          .attr("x", marginLeft)
          .attr("y", marginTop)
          .attr("width", width - marginLeft - marginRight)
          .attr("height", height - marginTop - marginBottom)
          .attr("preserveAspectRatio", "none")
          .attr(
            "xlink:href",
            this.legendConstruction(legendColor.interpolator()).toDataURL()
          );

        legendSvg
          .append("g")
          .attr("transform", `translate(0,${height - marginBottom})`)
          .call(
            d3
              .axisBottom(x)
              .ticks(
                ticks,
                typeof tickFormat === "string" ? tickFormat : undefined
              )
              .tickFormat(
                typeof tickFormat === "function" ? tickFormat : undefined
              )
              .tickSize(tickSize)
              .tickValues(tickValues)
          )
          .call(tickAdjust)
          .call((g) => g.select(".domain").remove())
          .call((g) =>
            g
              .append("text")
              .attr("x", marginLeft)
              .attr("y", marginTop + marginBottom - height - 6)
              .attr("fill", "currentColor")
              .attr("text-anchor", "start")
              .attr("font-weight", "bold")
              .text(title)
          );
      } else {
        console.log("the data hasn't loaded in yet");
      }
    },
  },
  mounted() {
    this.showMap();
  },
  updated() {
    this.sourceLayer();
  },
};
</script>
<style scoped>
.legendwrapper {
  margin-top: 8vh;
  left: 1;
  padding: 10px;
  position: fixed;
  background-color: white;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
  border-radius: 2px;
  z-index: 999999;
}

.legend {
  padding: 5px 15px;
}
</style>
