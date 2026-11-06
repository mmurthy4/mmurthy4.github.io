
---
layout: page
title: "Homework 7: Bigfoot Sightings"
permalink: /homework7/
---

# Exploring Bigfoot Sightings Across the United States

This project investigates recorded Bigfoot sightings around the United States, using data from the Bigfoot Field Researchers Organization (BFRO). The two visualizations look at geographic patterns in reported sightings and how they've changed over time.

## Visualization 1: Bigfoot Sightings by State

<div id="chart1"></div>

The first visualization is a horizontal bar chart of the 15 states with the most recorded Bigfoot sightings. I used a bar chart to easily compare the number of reports across states and identify geographic patterns. On the y-axis, state names are encoded nominally, whereas on the x-axis, the number of sightings is encoded quantitatively. I picked a consistent steel-blue color rather than coloring each state differently because the main goal is to highlight variations in reported counts. In my Python notebook, I removed records with missing state information, grouped the remaining data by state, calculated the number of reports, and selected the 15 states with the highest totals. The chart also includes tooltips showing the exact number of sightings in each state.

## Visualization 2: Bigfoot Sightings Over Time

<div id="chart2"></div>

The second visualization is an interactive line chart that depicts how reported Bigfoot sightings have changed over time in individual states. I chose a line chart because it illustrates variations in reported sightings over time and makes trends or unusual spikes easier to identify. The x-axis encodes the year as ordinal data, whereas the y-axis encodes the number of sightings as quantitative data. To distinguish this visualization from the first chart, I chose a consistent orange color rather than introducing unnecessary color groupings. In Python, I converted the original date column to datetime values, removed records with missing dates or states, extracted the year, and grouped the reports by state and year to produce annual sighting counts.

Viewers can select a state from the interactive dropdown, and the line chart immediately updates to show only the reports for that state. This makes the visualization easier to explore because users can focus on particular states rather than interpreting dozens of overlapping lines. I also included tooltips that allow visitors to examine the state, year, and exact number of sightings.

## Data and Analysis

[The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv)

[The Analysis](https://github.com/mmurthy4/mmurthy4.github.io/blob/main/homework7.ipynb)

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#chart1', '{{ "/assets/json/homework7_chart1.json" | relative_url }}', {actions: false});
  vegaEmbed('#chart2', '{{ "/assets/json/homework7_chart2.json" | relative_url }}', {actions: false});
</script>
