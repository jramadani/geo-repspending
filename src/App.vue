<template>
  <div id="page-container">
    <div id="nav">
      <span class="title"
        >Dollars to Districts: A Geographic Analysis of Representative
        Spending</span
      >
      <span class="icons"
        ><a href="https://github.com/jramadani/geo-repspending"
          ><img src="../public/notes.svg" /> </a
        >&nbsp; &nbsp;&nbsp;&nbsp;<a
          href="https://github.com/jramadani/geo-repspending/tree/master/public"
          ><img src="../public/paper.svg" /></a
      ></span>
    </div>
    <div id="page-content">
      <Info
        :categories="categories"
        :maindata="maindata"
        :arrayComputation="arrayComputation"
        @stepcatcher="stepcatch = $event"
      />
      <USMap
        :spendata="spendata"
        :stepcatch="stepcatch"
        :categories="categories"
        :maindata="maindata"
      />
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
      categories: [],
      maindata: [],
    };
  },
  watch: {
    stepcatch(val, oldVal) {
      console.log(`new: ${val}, old: ${oldVal}`);
      console.log("here is the array with switched case", this.switchCase(val));
      this.maindata = this.switchCase(val);
    },
  },
  methods: {
    arrayComputation: function (value) {
      let localArray = [];
      d3.rollups(
        value,
        (v) => d3.sum(v, (d) => +d.amount),
        (d) => d.fullname,
        (d) => d.party,
        (d) => d.state,
        (d) => d.geoid
      )
        .map((d) => d.flat(6))
        .forEach((d) =>
          localArray.push({
            fullname: d[0],
            party: d[1],
            state: d[2],
            geoid: d[3],
            amount: d[4],
          })
        );
      console.log(localArray);
      return localArray;
    },
    switchCase: function (step) {
      switch (step) {
        case 2:
          console.log("this is the total spending!");
          return this.arrayComputation(this.spendata);
        case 4:
          console.log("this is the start of the categories");
          return this.arrayComputation(
            this.spendata.filter((d) => d.category == this.categories[0])
          );
        case 5:
          return this.arrayComputation(
            this.spendata.filter((d) => d.category == this.categories[1])
          );
        case 6:
          return this.arrayComputation(
            this.spendata.filter((d) => d.category == this.categories[2])
          );
        case 7:
          return this.arrayComputation(
            this.spendata.filter((d) => d.category == this.categories[3])
          );
        case 8:
          return this.arrayComputation(
            this.spendata.filter((d) => d.category == this.categories[4])
          );
        case 9:
          return this.arrayComputation(
            this.spendata.filter((d) => d.category == this.categories[5])
          );
        case 10:
          return this.arrayComputation(
            this.spendata.filter((d) => d.category == this.categories[6])
          );
        case 11:
          return this.arrayComputation(
            this.spendata.filter((d) => d.category == this.categories[7])
          );
        case 12:
          return this.arrayComputation(
            this.spendata.filter((d) => d.category == this.categories[8])
          );
      }
    },
  },
  mounted() {
    Promise.all([
      d3.csv(
        "https://raw.githubusercontent.com/jramadani/geo-repspending/master/public/repspending.csv",
        (d) => ({
          bioguideid: d.BIOGUIDE_ID,
          category: d.CATEGORY,
          amount: +d.AMOUNT,
          fullname: d.full_name,
          state: d.state,
          district: d.district.padStart(2, "0"),
          party: d.party,
          geoid: d.geoid.padStart(4, "0"),
        })
      ),
    ]).then(([data]) => {
      this.spendata = data;
      this.categories = d3
        .rollups(
          data,
          (v) => d3.sum(v, (d) => +d.amount),
          (d) => d.category
        )
        .sort((a, b) => d3.descending(a[1], b[1]))
        .map((d) => d[0]);
      console.log("spending data", this.spendata);
      console.log("categories: ", this.categories);
    });
  },
  // updated() {
  //   console.log("caught:", this.stepcatch);
  //   // if (this.stepcatch != null || 0) {
  //   //   console.log("stepcatch debug testing within app", this.stepcatch);
  //   // }
  // },
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
