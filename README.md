# Pivotal Cloud Foundry Metrics による アプリケーション診断
Pivotal Cloud Foundry Metrics を使用して、
Pivotal Cloud Foundry 上で実行しているアプリケーションのログ、メトリック、イベントデータを確認します。

## 概要 / 説明

### Pivotal Cloud Foundry Metrics
Pivotal Cloud Foundryとそのプラットフォーム上で稼働しているすべてのアプリケーションの
健全性とパフォーマンスを可視化し、次の課題に対する支援します。

- 何が、いつ問題になったのか？
  - アプリケーションメトリックがその答えを提示します。<br>メトリックは、長いネットワーク遅延が発生した場合のタイムウィンドウと平均応答時間を明示します。
- なぜ問題を起こしたか？
  - ログとメトリック (APIコール、正確な応答時間、渡されたパラメータなど) が、<br>なぜ遅延が発生したのかを解明するのに十分な情報を提供します。

#### Pivotal Cloud Foundry Metrics 表示情報

Pivotal Cloud Foundry Metricsは、次の情報を表示します。

- コンテナメトリック
  - CPU、メモリ、ディスク使用率のグラフ
- ネットワークメトリック：
  - リクエスト、HTTPエラー、応答時間のグラフ
- アプリケーションイベント
  - 更新、開始、停止、クラッシュ、SSH、ステージング失敗イベントのグラフ
- ログ
  - 追加の調査のために、検索、フィルタリング、ダウンロードが可能なアプリケーションログのリスト
- Trace Explore
  - アプリケーションとエンドポイント間のリクエストを、対応するログと共にトレースするグラフ

## 前提 / 環境
- [事前作業](https://github.com/shinyay/pcf-workshop-prerequisite/blob/master/README.md)

## 手順 / 解説
### アプリケーションの準備
モニタリングする対象のアプリケーションを作成し、Pivotal Cloud Foundry にデプロイを行います。

#### プロジェクトの作成
GitHub 上に作成済みのプロジェクトをクローン(git clone)しプロジェクトを作成します。

- https://github.com/shinyay/spring-music.git

任意のディレクトリで、以下のコマンドを実行します。

```
$ mkdir pcf-workshop
$ cd pcf-workshop
$ git clone https://github.com/shinyay/spring-music.git hello-pcf-metrics
$ cd hello-pcf-metrics
```

#### アプリケーションのビルド
クローンしてきたアプリケーションは、**Gradle** でビルドを行うように構成されています。

アプリケーションのビルドは、以下のコマンドを使用します。

```
$ ./gradlew clean assemble
```

## まとめ / 振り返り
