# dci-dashboard

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A web-based dashboard that visualizes the "Digital Competitiveness Index (DCI)" for all 47 prefectures in Japan.


![A screenshot of the dci-dashboard showing a map of Japan made of grid cells, each representing a prefecture. The cells are color-coded in shades of blue. A dropdown menu at the top allows selecting different metrics like 'DCI' or 'Internet usage'.](https://user-images.githubusercontent.com/1552733/279860167-17552528-98e1-4c60-843d-045053723048.png)


## Demo

**[https://code4fukui.github.io/dci-dashboard/](https://code4fukui.github.io/dci-dashboard/)**

## Features

-   **Multiple Metrics:** Visualize the overall DCI or its four sub-components: Internet Usage (ネット利用), Digital Public Services (デジタル公共サービス), Connectivity (コネクティビティ), and Human Capital (人的資本).
-   **Interactive Map:** A responsive, grid-based "tabular map" of Japan represents each prefecture.
-   **Color-Coded Rankings:** Prefectures are color-coded based on their score for the selected metric. A darker shade indicates a higher value and rank.
-   **Detailed Data on Click:** Click any prefecture to view its complete data profile in a simple alert pop-up.
-   **Lightweight:** Built with vanilla JavaScript and CSS, requiring no complex build steps or frameworks.

## How It Works

The application fetches prefecture data and renders a "tabular map" of Japan using CSS Grid. This map is defined by a [CSV layout file](https://tabularmaps.github.io/areamap/tabularmaps_japan.csv). Each prefecture's cell is then populated with its name, rank, and score, and its background color is calculated based on its value relative to the minimum and maximum scores for that metric.

## Data Source

This dashboard uses data from the "Digital Competitiveness Index (DCI) by prefecture" report published by the Nomura Research Institute (NRI).

-   **Original Report:** [野村総合研究所(NRI)による「DCIにみる都道府県別デジタル度」](https://www.nri.com/jp/knowledge/report/lst/2023/cc/0419_1)
-   **CSV Dataset:** The data is consumed from the [code4fukui/dci-stat](https://github.com/code4fukui/dci-stat) repository, which provides a machine-readable version of the report's findings.

The data is fetched directly in the browser via:
```javascript
const url = "https://code4fukui.github.io/dci-stat/dci.csv";
const data = await CSV.fetchJSON(url);
```

## Usage

Since this is a static web application, you can run it locally by simply cloning the repository and opening `index.html` in a modern web browser. No web server is required.

```bash
git clone https://github.com/code4fukui/dci-dashboard.git
cd dci-dashboard
# Open index.html in your browser
```

## License

MIT License — see [LICENSE](LICENSE).