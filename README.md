# Kunitaka Civic Tech: Kids Safe Map

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A community safety map for the Kunitaka district of Echizen City, Fukui, Japan. This project visualizes dangerous locations, school zones, and other local data to improve child safety.

## Live Demo

View the interactive map: **[https://code4fukui.github.io/kunitaka/](https://code4fukui.github.io/kunitaka/)**

The map displays various safety-related data points on a map of the Kunitaka area, with a distinctive red header and a side menu for layer selection.

## Features

-   **Interactive Safety Map:** Visualizes school zones, reported dangerous locations, streetlights, and traffic accident data.
-   **Easy Data Contribution:** Uses [Geo3x3](https://geo3x3.com/) codes to allow community members to easily pinpoint and report hazardous locations.
-   **Open Data:** Provides school zone route data as a GeoJSON file under a CC BY license.
-   **Data Processing Tools:** Includes a Jupyter Notebook for analyzing traffic accident data and a Deno script for converting Japanese geodetic coordinates (Tokyo Datum) to WGS84.

## How to Add a Dangerous Location

Community contributions are welcome. To add a new dangerous or concerning location to the map:

1.  Open the **[Latitude Longitude Map](https://fukuno.jig.jp/app/map/latlng/#Akechi)** app and navigate to the correct location.
2.  Copy the `Geo3x3` code provided by the app.

    
![image](https://user-images.githubusercontent.com/1715217/219602296-2d3b72ce-581a-4ba8-8c69-edbe1b95ee76.png)


3.  Add a new line to the appropriate CSV file in the `kidssafe/` directory with the Geo3x3 code, a description of the hazard, and a suggested improvement.
4.  Submit a pull request with your changes.

## Development

### Prerequisites

-   [GitHub Desktop](https://desktop.github.com/)
-   [Deno](https://deno.land/)

### Running Locally

1.  Clone the repository using GitHub Desktop by clicking the green "Code" button and selecting "Open with GitHub Desktop".
2.  In your terminal, navigate to the cloned `kunitaka` directory.
3.  Start the Deno live server:
    ```sh
    deno run --allow-net --allow-read https://taisukef.github.io/liveserver/liveserver.js
    ```
4.  Open the local URL displayed in your terminal (e.g., `http://[::]:7001/`).
5.  Edit files like `index.html`. The browser will automatically reflect your changes.
6.  Use GitHub Desktop to create a branch and submit a pull request with your code contributions.

## Data Processing

### Traffic Accident Analysis

The Jupyter Notebook `data_analyse.ipynb` is used to process traffic accident data.

1.  Install the required Python packages:
    ```sh
    python3 -m pip install pandas jupyter
    ```
2.  Start the Jupyter server:
    ```sh
    jupyter notebook
    ```
3.  Open `data_analyse.ipynb` from the Jupyter interface in your browser.

### Streetlight Coordinate Conversion

The script `streetlight/jp2wgs.js` converts streetlight coordinates from the Japanese Geodetic System to WGS84. It reads `k.csv` and writes the converted data to `k2.csv`.

## Open Data

-   **School Zone GeoJSON:** [https://code4fukui.github.io/kunitaka/schoolzone.geojson](https://code4fukui.github.io/kunitaka/schoolzone.geojson) (CC BY)

## License

MIT License