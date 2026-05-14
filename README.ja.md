# Kunitakaシビックテック: キッズセーフマップ

福井県越前市国高地区のコミュニティ安全マップです。危険な場所や通学区域、その他の地域データを可視化し、児童の安全向上を目指しています。

## ライブデモ

インタラクティブマップはこちら: **[https://code4fukui.github.io/kunitaka/](https://code4fukui.github.io/kunitaka/)**

国高エリアの地図上に様々な安全関連のデータポイントを表示し、特徴的な赤色のヘッダーとレイヤー選択用のサイドメニューを備えています。

## 主な機能

- **インタラクティブ安全マップ:** 通学区域、報告済みの危険箇所、街路灯、交通事故データを可視化します。
- **手軽なデータ追加:** [Geo3x3](https://geo3x3.com/)コードを使用し、地域住民が簡単に危険箇所を特定・報告できるようにしています。
- **オープンデータ:** 通学区域のルートデータをCC BYライセンスのGeoJSONファイルとして提供しています。
- **データ処理ツール:** 交通事故データ分析用のJupyter Notebookと、日本測地系（Tokyo Datum）の座標をWGS84に変換するDenoスクリプトが含まれています。

## 危険箇所の追加方法

皆様からのデータ提供を歓迎します。マップに新たな危険箇所や気になる場所を追加するには、以下の手順に従ってください:

1. **[緯度経度マップ](https://fukuno.jig.jp/app/map/latlng/#Akechi)** アプリを開き、該当する場所に移動します。
2. アプリ上に表示される `Geo3x3` コードをコピーします。

![image](https://user-images.githubusercontent.com/1715217/219602296-2d3b72ce-581a-4ba8-8c69-edbe1b95ee76.png)

3. `kidssafe/` ディレクトリ内の適切なCSVファイルに、Geo3x3コード、危険箇所の説明、改善提案を含む新しい行を追加します。
4. 変更内容を含めてプルリクエストを送信します。

## 開発

### 前提条件

- [GitHub Desktop](https://desktop.github.com/)
- [Deno](https://deno.land/)

### ローカルでの実行方法

1. 緑色の「Code」ボタンをクリックし、「Open with GitHub Desktop」を選択して、GitHub Desktopでリポジトリをクローンします。
2. ターミナルで、クローンした `kunitaka` ディレクトリに移動します。
3. Denoのライブサーバーを起動します:
    ```sh
    deno run --allow-net --allow-read https://taisukef.github.io/liveserver/liveserver.js
    ```
4. ターミナルに表示されたローカルURL（例: `http://[::]:7001/`）を開きます。
5. `index.html` などのファイルを編集すると、ブラウザに変更が自動的に反映されます。
6. GitHub Desktopを使用してブランチを作成し、コードの変更を含むプルリクエストを送信します。

## データ処理

### 交通事故データの分析

交通事故データの処理には、Jupyter Notebookの `data_analyse.ipynb` を使用します。

1. 必要なPythonパッケージをインストールします:
    ```sh
    python3 -m pip install pandas jupyter
    ```
2. Jupyterサーバーを起動します:
    ```sh
    jupyter notebook
    ```
3. ブラウザのJupyterインターフェースから `data_analyse.ipynb` を開きます。

### 街路灯の座標変換

スクリプト `streetlight/jp2wgs.js` は、街路灯の座標を日本測地系からWGS84に変換します。`k.csv` を読み込み、変換後のデータを `k2.csv` に書き出します。

## オープンデータ

- **通学区域GeoJSON:** [https://code4fukui.github.io/kunitaka/schoolzone.geojson](https://code4fukui.github.io/kunitaka/schoolzone.geojson) (CC BY)

## ライセンス

MIT License
