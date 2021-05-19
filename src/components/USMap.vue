<template>
  <div id="map-container">{{ update() }}</div>
</template>
<script>
import * as d3 from "d3";
import "mapbox-gl/dist/mapbox-gl.css";
import mapboxgl from "mapbox-gl";

const height = window.innerHeight;

export default {
  name: "USMap",
  props: ["stepcatch", "spendata"],
  data() {
    return {
      zipmap: {},
      colorcode: [],
    };
  },
  methods: {
    showMap: function () {
      const mapcont = d3.select("#map-container");
      mapcont.attr("height", height * 0.9);
      mapboxgl.accessToken =
        "pk.eyJ1IjoianJhbWFkYW5pIiwiYSI6ImNrOW9xbWtmMzAxczYzZnA4bGlib2s3ZGgifQ.ZNLlxgGb_C51ZEzEGoPfbg";
      this.zipmap = new mapboxgl.Map({
        container: "map-container",
        style: "mapbox://styles/jramadani/ckorze9cn473w17qtztugvpgf", // stylesheet location
        center: [-70, 45], // starting position [lng, lat]
        zoom: 2.5, // starting zoom
      });
      console.log("zip interior check", this.zipmap);

      this.zipmap.on("load", () => {
        this.zipmap.addSource("tl_2020_us_state-2j4ve4", {
          type: "vector",
          url: "mapbox://jramadani.8g7q81yn",
        });
        this.zipmap.addLayer({
          id: "USstates",
          type: "fill",
          source: "tl_2020_us_state-2j4ve4",
          "source-layer": "tl_2020_us_state-2j4ve4",
          paint: {
            "fill-outline-color": "rgba(0,0,0,0.1)",
            "fill-color": "rgba(0,0,0,0.1)",
          },
        });
        if (this.spendata != null && this.colorcode.length > 0) {
          this.update();
          this.mapColorUpdate();
        }
      });
    },
    update: function () {
      console.log("step: ", this.stepcatch);
      console.log(
        "test limits of data",
        d3.extent(this.spendata, (d) => d.amount)
      );

      //GEOID VERSION
      //   if (this.spendata != null) {
      //     let color = d3
      //       .scaleSequential()
      //       .domain([0, d3.max(this.spendata, (d) => d.amount)])
      //       .range(["#6ea5c6", "#494197"]);
      //     let emptyArray = [];

      //     const intersperse = this.spendata.reduce((acc, property) => {
      //       const geo = `${property.geoid}`;
      //       acc[geo] = color(property.amount);
      //       return acc;
      //     }, {});
      //     const ia = Object.entries(intersperse);
      //     const step = ia.map((d) => [d[0], d[1]]);
      //     let flattening = step.flat();
      //     flattening.unshift("match", ["get", "GEOID"]);
      //     flattening.push("rgba(0,0,0,0)");

      //     flattening.forEach((d) => {
      //       if (d == "rgb(0, 0, 0)") {
      //         emptyArray.push("rgb(50, 7, 118)");
      //       } else {
      //         emptyArray.push(d);
      //       }
      //     });
      //     console.log(emptyArray);
      //   }

      if (this.spendata != null) {
        console.log("is spendata working?", this.spendata);
        let cc = [];
        let statespending = d3.rollups(
          this.spendata,
          (v) => d3.sum(v, (d) => +d.amount),
          (d) => d.state
        );
        console.log(statespending);
        console.log(d3.extent(statespending.map((d) => Math.round(d[1]))));

        let color = d3
          .scaleSequential()
          .domain(d3.extent(statespending.map((d) => Math.round(d[1]))))
          .range(["#295969", "#4EB6C6"]);

        const intersperse = statespending.reduce((acc, d) => {
          const st = `${d[0]}`;
          acc[st] = color(d[1]);
          return acc;
        }, {});
        console.log(intersperse);
        const ia = Object.entries(intersperse);
        let flattening = ia.flat();
        flattening.unshift("match", ["get", "STUSPS"]);
        flattening.push("rgba(0,0,0,0)");

        flattening.forEach((d) => {
          if (d == "rgb(0, 0, 0)") {
            cc.push("rgb(50, 7, 118)");
          } else {
            cc.push(d);
          }
        });
        console.log(cc);
        this.colorcode = cc;
        console.log(this.colorcode);
        // this.mapColorUpdate();
      }
    },
    mapColorUpdate: function () {
      console.log(this);
      if (this.zipmap.getLayer("selected-spending")) {
        this.zipmap.removeLayer("selected-spending");
      }
      //  MAP -- REDRAWN WITH COLOR LAYERS

      this.zipmap.addLayer({
        id: "selected-spending",
        source: "tl_2020_us_state-2j4ve4",
        "source-layer": "tl_2020_us_state-2j4ve4",
        type: "fill",
        paint: {
          "fill-color": this.colorcode,
          "fill-opacity": 0.8,
        },
      });
    },
  },
  mounted() {
    this.showMap();
  },
  updated() {
    if (this.stepcatch == 2) {
      console.log("i can see the event!");
      console.log("testing updates: ", this.zipmap);
    }
  },
};
</script>
<style scoped></style>
