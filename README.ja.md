# dci-dashboard

日本の47都道府県の「デジタル度（DCI: Digital Competitiveness Index）」を可視化するWebベースのダッシュボードです。

![dci-dashboardのスクリーンショット。グリッドセルで構成された日本地図を表示しており、各セルが都道府県を表しています。セルは青色の濃淡で色分けされています。上部のドロップダウンメニューで「DCI」や「ネット利用」などの指標を選択できます。](https://user-images.githubusercontent.com/1552733/279860167-17552528-98e1-4c60-843d-045053723048.png)

## デモ

**[https://code4fukui.github.io/dci-dashboard/](https://code4fukui.github.io/dci-dashboard/)**

## 機能

- **複数の指標:** 総合的なDCI、または4つのサブコンポーネント（ネット利用、デジタル公共サービス、コネクティビティ、人的資本）を可視化します。
- **インタラクティブな地図:** レスポンシブなグリッドベースの日本の「カラム地図（Tabular Map）」で各都道府県を表現します。
- **色分けされたランキング:** 選択した指標のスコアに基づいて都道府県を色分けします。色が濃いほど、値と順位が高いことを示します。
- **クリックで詳細データを表示:** 任意の都道府県をクリックすると、シンプルなアラートダイアログでその都道府県の完全なデータプロファイルを表示します。
- **軽量:** Vanilla JSとCSSで構築されており、複雑なビルド手順やフレームワークは必要ありません。

## 動作原理

本アプリケーションは、都道府県のデータを取得し、CSS Gridを使用して日本の「カラム地図」をレンダリングします。この地図は[CSVレイアウトファイル](https://tabularmaps.github.io/areamap/tabularmaps_japan.csv)によって定義されています。各都道府県のセルには名前、順位、スコアが表示され、背景色はその指標の最小値と最大値に対する相対的な値に基づいて計算されます。

## データソース

このダッシュボードは、野村総合研究所（NRI）が発表した「DCIにみる都道府県別デジタル度」レポートのデータを使用しています。

- **オリジナルレポート:** [野村総合研究所(NRI)による「DCIにみる都道府県別デジタル度」](https://www.nri.com/jp/knowledge/report/lst/2023/cc/0419_1)
- **CSVデータセット:** データは [code4fukui/dci-stat](https://github.com/code4fukui/dci-stat) リポジトリから取得しています。このリポジトリでは、レポートの結果を機械可読な形式で提供しています。

データは以下のコードにより、ブラウザ上で直接取得されます。
```javascript
const url = "https://code4fukui.github.io/dci-stat/dci.csv";
const data = await CSV.fetchJSON(url);
```

## 使い方

本アプリケーションは静的なWebアプリケーションであるため、リポジトリをクローンし、モダンWebブラウザで `index.html` を開くだけでローカルで実行できます。Webサーバーは必要ありません。

```bash
git clone https://github.com/code4fukui/dci-dashboard.git
cd dci-dashboard
# index.htmlをブラウザで開く
```

## ライセンス

MIT License — 詳細は [LICENSE](LICENSE) を参照してください。
