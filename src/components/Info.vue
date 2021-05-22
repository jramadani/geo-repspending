<template>
  <div id="info-container">
    <div id="instructions"><p>Scroll below to advance the story!</p></div>
    <div id="info-track">
      <section>
        <div class="info-box" data-step="1">
          <p>
            When it comes to budgetary spending, there is one golden rule: you
            spend more, you get more. This holds true for most budgets,
            including those of our representatives in Congress. Considering that
            our tax dollars are what these budgets consist of, we might want to
            know how much our representatives are spending, and on what.
          </p>
          <p>
            On the other hand, the United States is a purposefully large
            republic with a wide range of cultural differences and a variety of
            needs—so
            <b
              >to what extent does geography factor into our representatives’
              budgetary spending habits?</b
            >
            Let's find out!
          </p>
        </div>
      </section>
      <section>
        <div id="waypoint" class="info-box" data-step="2">
          <p>
            As you can see from how detailed the map to your left is, we’re
            going to be working on a district-level basis. This is because, as
            you’ll shortly see, the top spenders can make a state seem like a
            bigger spender than it actually is.
          </p>
          <p class="table-1"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="3">
          <p>
            This map shows the total amount that congressional representatives
            have reported spending so far in 2020.
          </p>
          <p>
            You can click and drag the map on the left, or zoom in to look at
            specific districts. This particular map reveals that, while all
            representatives spend a lot, the highest spenders represent
            districts that are from large states, or districts notable for
            containing big cities. Below you’ll find a table listing the top
            five spenders.
          </p>
          <p class="table-2"></p>
        </div>
      </section>
      <section>
        <div class="info-box" data-step="4">
          <p>
            Why are these representatives reporting so much spending? What do
            representatives from California, Texas, and New York have in common?
            Let’s drill down into some categories and see what’s going on.
          </p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="5">
          <p>
            The category that representatives spend the most on is personnel
            compensation, which makes sense given that most salaries are in
            range of 30,000 and above. However, because representatives are
            given a specific amount to spend based on population of their
            district (per the
            <a
              href="https://www.house.gov/the-house-explained/open-government/statement-of-disbursements/glossary-of-terms"
              >glossary of spending from the House of Representatives</a
            >), this map doesn’t hold much useful information. Below is a table
            showing the top five spenders on personnel compensation.
          </p>
          <!-- <Table :maindata="maindata" /> -->
          <p class="table-3"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="6">
          <p>
            Those representatives who are the highest spenders in terms of rent,
            communications, and utilities are from tiny districts near highly
            populated cities—you can see small brightly colored “hot spots”
            around those cities in places like California and Texas. Click on a
            district on the map that you’re interested in to see more
            information about the representative and the amount spent.
          </p>
          <p class="table-4"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="7">
          <p>
            Printing is the next highest category in terms of spending, and it’s
            a bit of a mixed bag. According to the House of Representatives’
            glossary of terms, printing can include “newsletters, postal patron
            mailings, mass mailings, notices of town hall meetings or notices of
            personal appearance of the Member at an official event,
            administrative papers (casework tracking forms, personnel record
            forms, etc.), legislative papers (bills, drafts, summaries,
            amendments, etc.), business cards for Members and their employees,
            stuffing, sealing and associated expenses relating to printing and
            sending official mail,” among other things. The highest spenders in
            this category are, strangely enough, representing some unexpected
            locations.
          </p>
          <!-- <Table :maindata="maindata" /> -->
          <p class="table-5"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="8">
          <p>
            “Other Services” sounds like a very nebulous category, and it can
            be—the House of Representatives defines this category as
            “obligations for contractual services including training.”
            Basically, whenever representatives reimburse tuition for their
            staff or hire a firm to provide services for them, they mark the
            spending down in this category. The highest spenders in this
            category are in populous cities regardless of party—zoom in on NYC,
            San Jose, and Houston to check out the highlights!
          </p>
          <p class="table-6"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="9">
          <p>
            Franked mail is a fascinating category. Defined by the House as
            reimbursable “postage expenses of specific pieces of mail sent out
            by Members,” franking privileges tend to be how incumbents can get a
            leg up on their opponents when it comes time for re-election. While
            you can’t get campaign materials reimbursed, franking privileges
            give incumbents name recognition. Little wonder, then, that the
            highest spenders in this category tend to be Republicans in
            geographically small city districts—an indication that they’re
            trying to hang on tight to those districts.
          </p>
          <p class="table-7"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="10">
          <p>
            If you’ve ever worked in an office, you know what spending on
            supplies entails. It’s your standard trip to Staples to get
            highlighters, binder clips, and anything else you might need in the
            normal course of business. The map might seem surprising, but this
            may be more of an indication that most of those representatives
            <a
              href="https://www.propublica.org/article/update-on-house-disbursements-a-few-notes-on-how-to-use-the-data"
              >haven’t gotten their receipts in on time for reporting!</a
            >
          </p>
          <p class="table-8"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="11">
          <p>
            Something that might not be apparent at first glance when
            considering spending on travel is that when representatives get
            reimbursed for travel expenses, this also includes meals! Our
            highest spenders here tend to be representing large districts in big
            states (e.g. KS, AZ, TX). This makes some sense when considering
            that representatives can sometimes go back to their districts to
            hear constituents’ concerns.
          </p>
          <p class="table-9"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="12">
          <p>
            Equipment is a fairly standard category—it describes spending on
            things like computers and hardware, items that the representative
            and their staff can use for a while. More spending in this category
            tends to be done by representatives from smaller districts
            (indicating more populous cities).
          </p>
          <p class="table-10"></p>
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="13">
          <p>
            "Transportation of Things" is the final category, and it’s
            incredibly sparse. Either representatives don’t tend to get their
            receipts to the clerk for this category, or they just don’t spend
            enough on transporting items—this is to the extent that the House
            doesn’t have a definition of what this category entails! What data
            we <i>do</i> have on this, however, shows that this kind of spending
            has not been done or reported in the Northwest in 2020.
          </p>
          <p class="table-11"></p>
        </div>
      </section>
      <section>
        <div class="info-box" data-step="14">
          <p>
            We’ve seen that geography can play an incredibly informative role
            when it comes to representative spending, depending on what they’re
            spending their budgets on. Though the data isn’t perfect, the
            general trend has been that representatives who spend more tend to
            be representing either very large districts or tiny districts that
            slice up populous cities.
          </p>
          <p>
            Categorically, we’ve also seen that geography tends to influence how
            much a representative will spend in the course of engaging with
            their constituents. Whether it’s purchasing hardware for the
            representative’s office so they can communicate with constituents
            hundreds of miles away or buying plane tickets to get to California
            from Washington, DC, there is definitely an impact from geography in
            certain types of spending.
          </p>
          <p>
            As a bit of a parting note, bear in mind that per ProPublica’s
            investigation into the data, house members are allowed to continue
            to report disbursements up to three years after they were made, so
            it’s entirely likely that this isn’t the full extent of the
            data—it’s just everything the representatives in 2020 decided to
            report so far!
          </p>
        </div>
      </section>
      <section>
        <div class="info-box" data-step="15">
          <p>
            To find out more about the 116th Congress and representative
            spending, you can visit
            <a
              href="https://www.house.gov/the-house-explained/open-government/statement-of-disbursements"
              >the official House Disbursements page</a
            >
            and inspect the original PDFs for this year.
          </p>

          <p>
            You can also visit
            <a href="https://projects.propublica.org/represent/expenditures"
              >ProPublica</a
            >
            to read more about how the data was initially scraped and processed.
          </p>

          <p>
            The data documentation and white paper for this project are in the
            header and link to this site’s GitHub repository, where you can
            check out the code for this project as well.
          </p>
        </div>
      </section>
    </div>
  </div>
</template>
<script>
// import Table from "./Table.vue";
import * as d3 from "d3";
import "intersection-observer";
import scrollama from "scrollama";
const scroller = scrollama();

export default {
  name: "Info",
  // components: { Table },
  props: ["maindata", "categories", "arrayComputation"],
  emits: ["stepcatcher"],
  data() {
    return {
      step: null,
      columns: ["Representative", "Party", "State", "Geoid", "Amount"],
      tabledata: [],
      classes: [],
      localdata: [],
    };
  },
  methods: {
    scroll: function () {
      console.log(this);
      scroller
        .setup({
          step: "#info-track section .info-box",
          debug: true,
          offset: 0.5,
        })
        .onStepEnter((response) => {
          this.step = response.index;
          console.log(this.step);
        });
    },
    classGen: function () {
      //classes setup
      const range = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11];
      range.forEach((d) => this.classes.push(".table-" + d));
      console.log(this.classes);
    },
    stateGen: function () {},
    allGen: function () {
      //setup data
      const pdata = this.arrayComputation(this.localdata);
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());

      console.log("testing all gen", td);
      //create table
      const table = d3
        .select(this.classes[1])
        .append("table")
        .attr("class", "table-dist");
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
    },
    pcGen: function () {
      //setup data
      const pdata = this.arrayComputation(
        this.localdata.filter((d) => d.category == this.categories[0])
      );
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);

      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
      //create table
      const table = d3
        .select(this.classes[2])
        .append("table")
        .attr("class", "table-dist");
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
    },
    rentGen: function () {
      //setup data
      const pdata = this.arrayComputation(
        this.localdata.filter((d) => d.category == this.categories[1])
      );
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);

      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
      //create table
      const table = d3
        .select(this.classes[3])
        .append("table")
        .attr("class", "table-dist");
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
    },
    printGen: function () {
      //setup data
      const pdata = this.arrayComputation(
        this.localdata.filter((d) => d.category == this.categories[2])
      );
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);

      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
      //create table
      const table = d3
        .select(this.classes[4])
        .append("table")
        .attr("class", "table-dist");
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
    },
    osGen: function () {
      //setup data
      const pdata = this.arrayComputation(
        this.localdata.filter((d) => d.category == this.categories[3])
      );
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);

      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
      //create table
      const table = d3
        .select(this.classes[5])
        .append("table")
        .attr("class", "table-dist");
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
    },
    fmGen: function () {
      //setup data
      const pdata = this.arrayComputation(
        this.localdata.filter((d) => d.category == this.categories[4])
      );
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);

      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
      //create table
      const table = d3
        .select(this.classes[6])
        .append("table")
        .attr("class", "table-dist");
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
    },
    spGen: function () {
      //setup data
      const pdata = this.arrayComputation(
        this.localdata.filter((d) => d.category == this.categories[5])
      );
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);

      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
      //create table
      const table = d3
        .select(this.classes[7])
        .append("table")
        .attr("class", "table-dist");
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
    },
    travGen: function () {
      //setup data
      const pdata = this.arrayComputation(
        this.localdata.filter((d) => d.category == this.categories[6])
      );
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);

      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
      //create table
      const table = d3
        .select(this.classes[8])
        .append("table")
        .attr("class", "table-dist");
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
    },
    equipGen: function () {
      //setup data
      const pdata = this.arrayComputation(
        this.localdata.filter((d) => d.category == this.categories[7])
      );
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);

      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
      //create table
      const table = d3
        .select(this.classes[9])
        .append("table")
        .attr("class", "table-dist");
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
    },
    tspGen: function () {
      //setup data
      const pdata = this.arrayComputation(
        this.localdata.filter((d) => d.category == this.categories[8])
      );
      const format = d3.format(",." + d3.precisionFixed(1) + "f");
      const td = pdata
        .sort((a, b) => d3.descending(a.amount, b.amount))
        .slice(0, 5);

      const colorScale = d3
        .scaleSequential()
        .domain(d3.extent(td, (d) => d.amount))
        // .range(["#1b2a36", "#355c6b", "#31a2ab", "#28c5d1", "#fffbe6"]);
        // .range(["#000027", "#003756", "#00798a", "#28c5d1", "#dbffff"]);
        .range(["#0d9ca2", "#49a9ab", "#70b5b5"].reverse());
      //create table
      const table = d3
        .select(this.classes[10])
        .append("table")
        .attr("class", "table-dist");
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
      this.localdata = data;
      this.scroll();
      this.classGen();
      this.allGen();
      this.pcGen();
      this.rentGen();
      this.printGen();
      this.osGen();
      this.fmGen();
      this.spGen();
      this.travGen();
      this.equipGen();
      this.tspGen();
    });
  },
};
</script>
<style scoped>
#info-track {
  background-color: rgba(255, 255, 255, 0.38);
  scroll-behavior: smooth;
  overflow-y: scroll;
  scrollbar-width: none;
  height: 88vh;
  height: fit-content;
}

::-webkit-scrollbar {
  display: none;
}
.info-box {
  margin: 2vw;
  background-color: #1b2a36;
  padding: 3vw;
  border-radius: 28px;
  color: #fffbe6;
}

section {
  min-height: 100vh;
  padding: 10vw 5vh;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  box-sizing: border-box;
}
#instructions {
  background-color: #28c5d1;
  height: 8vh;
  position: fixed;
  width: 40%;
  /* margin: auto; */
  display: grid;
}
#instructions p {
  color: #1b2a36;
  z-index: 999;
  position: fixed;
  text-align: center;
  /* margin: auto; */
  justify-self: center;
}
a {
  color: #28c5d1;
}
</style>
