<template>
  <p class="table-spending"></p>
</template>
<script>
import * as d3 from "d3";

export default {
  name: "Table",
  props: ["maindata"],
  data() {
    return {
      tabledata: [],
      columns: ["Representative", "Party", "State", "Geoid", "Amount"],
    };
  },
  methods: {
    tableGen: function () {
      if (this.maindata != undefined && this.maindata.length > 0) {
        // if (table) {
        //   d3.selectAll(table).remove();
        // }
        const table = d3
          .select("p")
          .append("table")
          .attr("class", "table-dist");
        // console.log("i'm in table", this.maindata);
        this.tabledata = this.maindata;
        const td = this.tabledata
          .sort((a, b) => d3.descending(a.amount, b.amount))
          .slice(0, 5);
        const format = d3.format(",." + d3.precisionFixed(1) + "f");
        console.log(
          "table color extent",
          d3.extent(td, (d) => d.amount)
        );
        const colorScale = d3
          .scaleSequential()
          .domain(d3.extent(td, (d) => d.amount))
          // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
          // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
          .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
        table
          .append("thead")
          .append("tr")
          .selectAll("th")
          .data(this.columns)
          .join("th")
          .text((d) => d)
          .style("font-size", "16px");

        let rows = table
          .append("tbody")
          .selectAll("tr")
          .data(td)
          .join("tr")
          .style("background-color", (d) => colorScale(d.amount))
          .style("color", "#eee");

        rows
          .selectAll("td")
          .data((d) => Object.values(d))
          .join("td")
          .text((d) => (typeof d === "string" ? d : format(d)))
          .style("font-size", "14px")
          .style("padding", ".7em");

        // rows.on("mouseover", (d) => {
        //   console.log("this is a table row", d);
        //   d3.select(d.srcElement.parentElement).style(
        //     "background-color",
        //     "blue"
        //   );
        // });
      }
    },
  },
  mounted() {
    this.tableGen();
  },
};
</script>
<style scoped>
thead,
tbody tr {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-bottom: 1px solid white;
}

tbody {
  width: 100%;
  display: block;
  height: 70vh;
  overflow: scroll;
}

th,
td {
  text-align: left;
  padding: 1em;
  cursor: pointer;
  font-weight: lighter;
  text-transform: capitalize;
}

td:hover {
  font-weight: 900;
  background-color: blue;
}

/* Count styles */
#count {
  display: flex;
  flex-direction: row;
}
</style>
