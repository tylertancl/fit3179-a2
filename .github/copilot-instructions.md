# AI Agent Instructions for the FIT3179-A2 Project

This document provides guidance for AI agents working on this data visualization project.

## Project Overview

This is a static data visualization project that uses HTML, JavaScript, and the Vega-Lite library to display information about the Tokyo 2020 Olympics. The goal is to present a series of charts on a single webpage.

- **Main Page**: `index.html` is the primary file that structures the page and embeds the charts.
- **Visualizations**: Charts are defined using the Vega-Lite specification and stored as individual `.vg.json` files in the `charts/` directory.
- **Data**: The data for the visualizations is stored in CSV format in the `data/` directory.

## Key Technologies

- **Vega-Lite**: This is the core library used for creating all visualizations. When asked to modify or create a chart, you should edit the corresponding `.vg.json` file according to the Vega-Lite grammar. You can find extensive documentation and examples on the [Vega-Lite website](https://vega.github.io/vega-lite/).
- **Vega-Embed**: This JavaScript library is used in `index.html` to load the Vega-Lite JSON definitions and render them into the specified `div` elements.

## Development Workflow

1.  **Running the Project**: There is no build step. To view the project, simply serve the root directory with a local web server. The VS Code "Live Server" extension is a good option for this.
2.  **Modifying a Chart**: To change an existing visualization, locate its definition file in the `charts/` directory (e.g., `chart1_medals_top20.vg.json`) and edit the JSON. The changes will be reflected when you refresh `index.html` in the browser.
3.  **Adding a New Chart**:
    - Create a new `.vg.json` file in the `charts/` directory with a valid Vega-Lite specification.
    - Add a new `<section>` and a `<div>` with a unique ID to `index.html`.
    - Add a `vegaEmbed(...)` call in the script tag at the bottom of `index.html` to link your new chart JSON to the new `div`.

## File Conventions

- **Chart Files**: Chart definition files are named descriptively and placed in the `charts/` directory (e.g., `chart1_medals_top20.vg.json`).
- **Data Files**: Data is sourced from CSV files in the `data/` directory. Chart definitions reference these files using a relative path (e.g., `"url": "../data/medals_total.csv"`). Note the `../` is not needed if the `data` folder is at the same level as the `charts` folder, but the current chart files use a relative path from within the `charts` directory. The paths in the JSON files are relative to the `index.html` file, so they should be `data/file.csv`.
