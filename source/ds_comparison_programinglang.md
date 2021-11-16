---
date    : 2021-11-11
title   : 【📊 DS】データサイエンスで使われる言語あれこれ
excerpt :
tags    : ["DataScientist", "SAS", "SPSS", "R", "Python"]
---

## || あらまし
最近、データサイエンス業界で何かとトレンディーな **Pyhotn**。<br>
絶賛「カッケー！」と言いながら勉強している自分ですが、<br>
先日上司とお話しをしていて、

「SASとPyhotnの違いわかる？」と聞かれ、

「...（いや分かんねー）。」となり
気になることがあったので調べてみた。

SASのイメージとしては、大学院生の修士で使われたり、大企業の分析担当者が用いているイメージ。
正直、バカ高いライセンス料金を払ってしか使えないなんて、今時じゃないし、なんで未だに使われているのか不明だったが、バカ高いにも理由があり、それも、オープンソースであるPythonとの明確な違いがここにあった。

**プログラミングのコードに対しての保証**。

ミスの許されない大企業、に好まれる点は、ここに有ると学んだ。

## || 言語間の差異
### | SAS
> SASは、データ管理、高度な分析、多変量分析、ビジネスインテリジェンス、犯罪調査、および予測分析のためにSASInstituteによって開発された統計ソフトウェアスイートです。 SASは、1966年から1976年にSAS Instituteが設立されるまで、ノースカロライナ州立大学で開発されました。
>
> ー [SAS (software)](https://en.wikipedia.org/wiki/SAS_(software))- Wikipedia（英語）

### | SPSS
> SPSSは、IBMの統計解析ソフトウェアの製品群。 当初は独立した会社の社名および製品名であったが、2009年のIBMによる買収以降は、IBMの製品名となった。
>
> ー [SPSS](https://ja.wikipedia.org/wiki/SPSS) - Wikipedia

### | R
> R言語はオープンソース・フリーソフトウェアの統計解析向けのプログラミング言語及びその開発実行環境である。ファイル名拡張子は.r, .R, .RData, .rds, .rda。 R言語はニュージーランドのオークランド大学のRoss IhakaとRobert Clifford Gentlemanにより作られた。
>
> ー [R言語](https://ja.wikipedia.org/wiki/R%E8%A8%80%E8%AA%9E) - Wikipedia

### | Python
> Pythonはインタープリタ型の高水準汎用プログラミング言語である。グイド・ヴァン・ロッサムにより創り出され、1991年に最初にリリースされたPythonの設計哲学は、有意なホワイトスペースの顕著な使用によってコードの可読性を重視している。
>
> ー [Python](https://ja.wikipedia.org/wiki/Python) - Wikipedia

## || まとめ

|      |SAS|SPSS|R  |Pyhotn|
|:-:   |:-:|:-: |:-:|:-:   |
|誕生日|1966's|||1991's|
|親    |ノースカロライナ州立大学|IBM|Ross Ihaka<p>Robert Clifford Gentleman|グイド・ヴァン・ロッサム|
|出身地|||||
|お金  |有料|有料|無料|無料|

### | トレンド（2004年~2021年現在）
![](https://i.gyazo.com/4c000adbfa29074e2ee5b5c342a5de93.png)
```html
<script type="text/javascript" src="https://ssl.gstatic.com/trends_nrtr/2674_RC03/embed_loader.js"></script> <script type="text/javascript"> trends.embed.renderExploreWidget("TIMESERIES", {"comparisonItem":[{"keyword":"SAS","geo":"JP","time":"2004-01-01 2021-11-13"},{"keyword":"SPSS","geo":"JP","time":"2004-01-01 2021-11-13"},{"keyword":"R","geo":"JP","time":"2004-01-01 2021-11-13"},{"keyword":"Python","geo":"JP","time":"2004-01-01 2021-11-13"}],"category":0,"property":""}, {"exploreQuery":"date=all&geo=JP&q=SAS,SPSS,R,Python","guestPath":"https://trends.google.co.jp:443/trends/embed/"}); </script>
```

`Cf.`
* [R, Python, SAS, SPSSを現場のデータサイエンティストの視点で比べてみた](https://blog.exploratory.io/r-python-sas-spss%E3%82%92%E7%8F%BE%E5%A0%B4%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%B5%E3%82%A4%E3%82%A8%E3%83%B3%E3%83%86%E3%82%A3%E3%82%B9%E3%83%88%E3%81%AE%E8%A6%96%E7%82%B9%E3%81%A7%E6%AF%94%E3%81%B9%E3%81%A6%E3%81%BF%E3%81%9F-e90a4bacb876) -Medium
