---
date    : 2021-09-24
title   : 【📊 DS】DataLake、DataWearHouse、DataMart
excerpt : データの入り口から出口までの流れ（ちょいメモ）
tags    : ["DataScientist", "DataLake", "ETL", "DataWearHouse", "DataMart"]
---

    ■ 一連のSTORY

    [ 🌊 ] > [ 🎣 / 🔪 / 🚶 ‍] > [ 🏘 ] > [ 🗃 ]

    （なんかマイクラみたいなんだね。）

## || 🌊 Data Lake (DL)
> データレイク (Data lake) は構造化/非構造化データやバイナリ等のファイル含めたデータを一元的に格納するデータリポジトリ。一般的に、データレイクはレポート、可視化、分析、機械学習に利用されるエンタープライズのデータのコピーや返還後のデータを一カ所に集約する。
>
> データレイクはリレーショナルデータベースの構造化データ（列と行）や、半構造化データ（CSV、ログ、XML、JSON）、非構造化データ（Eメール、ドキュメント、PDF）、バイナリデータ（画像、音声、映像）を含めることができる。
>
> ー [データレイク - Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%82%A4%E3%82%AF)


2010年頃にデータレイクという概念が登場した。
データレイクは、多種多様なデータを格納する。
構造データのみならず、非構造データもローデータで格納する。

ただ、なんでもかんでもブチ込むと、データレイクもその美しさを保たず、データスワンプ（沼）へと変貌する。
水質汚染を無くすべく**データカタログ**なるものが大事とのこと。


**Cf.**
* [データレイクとクラウドサービス　～①データレイクの今までをおさらい～ - Gixo](https://www.gixo.jp/blog/10259/)
* [データレイクのガバナンス - IBM](https://www.ibm.com/jp-ja/analytics/use-cases/governing-data-lake)
* [データスワンプ - Realize](https://www.realize-corp.jp/glossary/data-swamp)
* [データカタログ - Realize](https://www.realize-corp.jp/glossary/data-catalog)

### | 🎣 ETL（Extract/ Transform/ Load）

Cf.
* [ETL（Extract/Transform/Load）とは？ - talend](https://www.talend.com/jp/resources/what-is-etl/)
* [ELTとETLの違い BIへの影響と最適なアプローチ - talend](https://www.talend.com/jp/resources/elt-vs-etl/)

## || 🏘 Data Wear House (DWH)
> データウェアハウスとは、直訳すれば「データの倉庫」である。利用者により定義範囲は異なるが、一般に時系列に整理された大量の統合業務データ、もしくはその管理システムを指す。
>
> 定義
データウェアの提唱はアメリカの計算機科学者ビル・インモン（英語版）(William H. Inmon)で、1990年の著作によれば、「データウェアハウスは、意志決定(Decision)のため、目的別(Purpose-oriented)に編成され、統合(Integrate)された時系列で、削除(Delete)や更新(Update)しないデータの集合体」とされる。
複数の基幹系システム（製造管理システム、販売管理システム、会計システムなど)から、トランザクション(取引)を抽出して、再構成・再蓄積したシステムを指すことが多い。
> ー [データウェアハウス - Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A6%E3%82%A7%E3%82%A2%E3%83%8F%E3%82%A6%E3%82%B9)

**Cf.**
* [データウェアハウス（DWH）とは？メリットや活用例まで一挙に紹介 - TopGate](https://www.topgate.co.jp/dwh-merits-case-study)
* [【意外と簡単？】オンプレミスの DWH から BigQuery へのデータ移行を徹底解説！ - TopGate](https://www.topgate.co.jp/migration-onpremises-to-bigquery)

## || 🗃 Data Mart (DM)
> 利用部門ごとに使用するデータや分析内容が異なることが多いため、その利用部門が必要とするデータのみをデータウェアハウスから抽出したり、その利用部門が必要とする分析データをあらかじめ集計することにより、分析レスポンスを向上できる。これは、データ容量が小さくなることやリクエストのたびに集計値を計算することがなくなるためにレスポンスが向上できることと、通常は利用部門ごとにサーバを設置するためにサーバ単位の同時ユーザ数が減るためでもある。
>
> ー [データマート - Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%87%E3%83%BC%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%88)


1. 従属型データマート

    使うデータをガチガチに定義してDWHから抽出。

2. 独立型データマート

    DWHを介さず単一のビジネス機能（サブジェクト領域）だけを対象として抽出。

3. ハイブリット型データマート

    DWHと運用元システムデータをがっちゃんこにして使う。

Cf.[データ分析基盤の基本と構築のポイント - Data Design](https://data.nifcloud.com/blog/data-analysis_basic_point/)

### | CDP（Customer Data Platform）
Cf. [データ統合に必要な仕組み Data Lake / ETL / DWH とCDPの構成 - Integral Core](https://cdp-integral.com/blog/dataintegration_datalake-etl-dwh-cdp)


---
## || ⚖️ 比較
### | DL - DWH
>||DL|DWH|
|-|-|-|
|データ構造|ローデータ|処理済みデータ|
|データの目的|未確定|現在使用中|
|ユーザー|データサイエンティスト|ビジネス担当者|
|アクセス性|高度にアクセス可能、迅速な更新|より複雑、変更のコストが高い|
>
> ー [データレイクとデータウェアハウス - talend](https://www.talend.com/jp/resources/data-lake-vs-data-warehouse/)

### | DWH - DM

>||DWH|DM|
|-|-|-|
|サイズ|100GB以上|100GB未満|
|サブジェクト|複数|単一|
|範囲|全社的|専門部門|
|データソース|多数|少数|
|データ結合|全てのビジネスデータ|単一サブジェクト領域|
|要構築時間|数ヵ月~数年|数分~数週間|
>
> ー [データマートとは？ - talend](https://www.talend.com/jp/resources/what-is-data-mart/)

---
## || データ分析基盤 - 一連の流れ
> ![img](https://data.nifcloud.com/wordpress/wp-content/uploads/2020/01/blog-image202001-1024x631.png)
>
> ー [データ分析基盤の基本と構築のポイント - Data Design](https://data.nifcloud.com/blog/data-analysis_basic_point/)


**Cf.**
* [リクルートライフスタイルが考える、万人に使ってもらえる分析基盤の作り方 - slide share](https://www.slideshare.net/yuyamada777/ss-98072988)
* [ビッグデータを“本当に”活用するためのクラウド基盤とは - マイナビ](https://news.mynavi.jp/kikaku/20190215-768056/)
