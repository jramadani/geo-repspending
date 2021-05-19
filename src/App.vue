<template>
  <div id="page-container">
    <div id="nav">
      <span class="title"
        >Dollars to Districts: A Geographic Analysis of Representative
        Spending</span
      >
      <span class="icons"
        ><a href=""><img src="../public/notes.svg" /> </a>&nbsp;
        &nbsp;&nbsp;&nbsp;<a href=""><img src="../public/paper.svg" /></a
      ></span>
    </div>
    <div id="page-content">
      <Info :spendata="spendata" @stepcatcher="stepcatch = $event" />
      <USMap :spendata="spendata" :stepcatch="stepcatch" />
    </div>
  </div>
</template>

<script>
import * as d3 from "d3";
import Info from "./components/Info.vue";
import USMap from "./components/USMap.vue";

export default {
  name: "App",
  components: {
    Info,
    USMap,
  },
  data() {
    return {
      spendata: [],
      stepcatch: null,
    };
  },
  methods: {},
  mounted() {
    Promise.all([
      d3.csv("repspending.csv", (d) => ({
        bioguideid: d.BIOGUIDE_ID,
        category: d.CATEGORY,
        amount: +d.AMOUNT,
        fullname: d.full_name,
        state: d.state,
        district: d.district.padStart(2, "0"),
        party: d.party,
        geoid: d.geoid.padStart(4, "0"),
      })),
    ]).then(([data]) => {
      this.spendata = data;
      console.log("spending data", this.spendata);
    });
  },
  updated() {
    console.log("caught:", this.stepcatch);
  },
};
</script>

<style>
body {
  /* overflow: hidden; */
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: 0;
  padding: 0;
  min-height: 110%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-size: 20px;
}

#page-container {
  display: grid;
  grid-template-rows: 8% auto;
}

#nav {
  background-color: #09141c;
  color: #fffbe6;
  grid-row-start: 1;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: grid;
  grid-template-columns: 1fr 1fr;
  font-family: "Crimson Text", serif;
  font-size: 1.25em;
  height: 8vh;
}

#page-content {
  background-color: skyblue;
  grid-row-start: 2;
  height: fit-content;
}

.title {
  align-self: center;
  justify-self: left;
  padding: 15px;
}

.icons {
  align-self: center;
  justify-self: right;
  padding: 15px 30px 15px 15px;
}

/* mobile media query */

/* @media screen and (max-aspect-ratio: 4/5) {


} */

/* desktop media query */

@media screen and (min-aspect-ratio: 4/5) {
  #info-container {
    position: fixed;
    right: 0;
    bottom: 0;
    height: 92vh;
    width: 40%;
    z-index: 720;
    overflow: auto;
    scrollbar-width: none;
  }
  #map-container {
    /* background-color: #fffbe6; */
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
    height: 92vh;
    width: 100%;
    z-index: 600;
  }
}
</style>
