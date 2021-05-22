# About this repository

This repository contains code for a narrative mapping project created for DATA 78000 with Professor Shipeng Sun. The project's deployed state [can be found here.](https://jramadani.github.io/geo-repspending)

## Dollars to Districts: a Geographic Analysis of Congressional Representative Spending

Dollars to Districts is a web project built using Vue, d3, and Mapbox GL JS. Initial data processing, cleaning, mapping, and exploration was done using QGIS.

### Abstract

When we do our taxes, we don't really think about the fact that those same taxes fund the budgets of our government. As a point of transparency, members of the House of Representatives are required by law to disclose their spending disbursements on an annual basis (though they have up to three years to actually report those disbursements). In order to hold our representatives accountable, it's important for us to know how, where, and why they spend their budgets. Dollars to Districts takes this premise and turns it on its head to ask a question not of corruption but of the side effects of the purposeful enormity of our republic: to what extent does geography factor into our representatives' budgetary spending habits?

### Background and Research Questions

James Madison wrote in Federalist #10 that a large republic was key to stopping the "vicious acts" of a majority in their tracks. However, having such a large republic has enormous side effects, and one of those side effects is that this country has a very diverse amount of situations encompassed within it. Districts can span thousands of miles or can be slivers of space, arranged in ways that make them look like a very glitched out Tetris puzzle (Gerrymandering is its own topic and will not be covered in this project).

To answer the overarching question of how much geography factors into our representatives' budgetary spending, this project also asks:

- Which states have the highest spending representatives?
- How big are those representatives' districts?
- Where are the districts located (in the cities or suburbs)?
- Do certain locations spend more on certain categories?
- Which districts spend more on which categories?

In the narrative, the project seeks to answer all of these questions as well as its overarching topic.

### The Website

Built in Vue, d3.js, and Mapbox, the site attempts to make this data as interactive as possible in the span of a semester.

#### Design

Many of the design elements of this project were conceived of deliberately. For example, Mapbox has a maximum zoom level for certain types of data, and in a browser window, you won't be able to see the entire United States. This is why the information pane is partially transparent, to allow the user to see beyond the extent of the open map pane. Additionally, the colors were selected to provide a slight twist on the green of money, and were tweaked multiple times to achieve clarity of information.

#### Coding

The site consists of one overarching app and two components that feed into the app (the information panel and the map). The information sections emit a number to the overarching app, which accepts the number, pushes it into a function that passes it through a set of switch-cases, and then assigns data to a variable on scroll. The data is then fed into the map, which passes it into a color function. This is the "engine" of the project, but there's definitely more under the hood, so to speak!

### Data & Methodology

[Please see this README file to find out more about the data and methodology](https://github.com/jramadani/geo-repspending/public/README.md).

### Potential Next Steps

One of my primary goals in creating this project on the web (rather than a blog post or a static poster) was to make the data interactive. In the future, I would like to make the tables interactive and, when the user hovers on them, to have the matching district's outline turn a different color, or to zoom to that district. As this was not possible in the timeframe of this project, I have placed it on a roadmap in future iterations of this project.

### Thank you!

Thanks for your interest in this project and repository!
