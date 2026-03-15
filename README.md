# Kunitaka Civic Tech

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

## Kidssafe MAP in Kunitaka

https://code4fukui.github.io/kunitaka/kidssafe.html

## Editing Dangerous Locations

Copy the Geo3x3 code from the "Latitude Longitude Map" app below for the corresponding location.
- https://fukuno.jig.jp/app/map/latlng/#Akechi

<img width="511" alt="image" src="https://user-images.githubusercontent.com/1715217/219602296-2d3b72ce-581a-4ba8-8c69-edbe1b95ee76.png">

## Open Data CC BY

- [School Zone GeoJSON](https://code4fukui.github.io/kunitaka/schoolzone.geojson)

## Development

### Clone the repository

1. Install [GitHub Desktop](https://desktop.github.com/)
2. Click the green "Code" button and select "Open with GitHub Desktop"
3. Install [Deno](https://deno.land/)
4. Run the following in the kunitaka directory:
```sh
deno run --allow-net --allow-read https://taisukef.github.io/liveserver/liveserver.js
```
5. Open the displayed link in a browser (e.g. [http://[::]:7001/](http://[::]:7001/))
6. Edit files such as `kidssafe.html` (changes will be automatically reflected in the browser)
7. Create a branch in GitHub Desktop and submit a pull request

## Traffic Accident Open Data Processing with Jupyter Notebook

```
python3 -m pip install pandas
python3 -m pip install jupyter
jupyter notebook
```
Open "data_analyse.ipynb"

## License

MIT License