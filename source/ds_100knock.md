---
date    : 2021-09-24
title   : 【📊 DS】データサイエンス100本ノック（構造化データ加工編）
excerpt : データサイエンス協会が、データサイエンス初学者のための実践的な学習環境をGitHubに無料公開！
tags    : ["DataScientist", "GitHub", "Docker", "SQL", "R", "Python"]
---

## || なにこれ
> 一般社団法人データサイエンティスト協会（所在地：東京都港区、代表理事：草野 隆史、以下データサイエンティスト協会）は、構造化データの加工について実践的に学ぶことができる無料の学習環境「データサイエンス100本ノック（構造化データ加工編）」をGitHubに公開しました。
>
>「データサイエンス100本ノック（構造化データ加工編）」は、データサイエンス初学者を対象に、データの加工・集計、統計学や機械学習を駆使したモデリングの前処理等を学べるよう、データと実行環境構築スクリプト、演習問題をワンセットにしています。
>
> _ー_ [データサイエンス初学者のための実践的な学習環境 「データサイエンス100本ノック（構造化データ加工編）」をGitHubに無料公開](https://digitalpr.jp/r/39499) - Digital PR Platform

GitHubは[こちら。](https://github.com/The-Japan-DataScientist-Society/100knocks-preprocess) (The-Japan-DataScientist-Society/100knocks-preprocess)

---
## || 事前準備（環境構築）
#### | 構築イメージ
> ![img](https://user.pr-automation.jp/simg/1731/39499/700_277_202006151645535ee727319bac0.JPG)
> ー [Digital PR Platform](https://digitalpr.jp/r/39499)

#### | 🐙GitHub
`$ mkdir plactice` 任意のディレクトリを作成。
`$ cd plactice/`移動して、
```SHELL
$ git clone https://github.com/The-Japan-DataScientist-Society/100knocks-preprocess
```

#### | 🐋Docker
`$ cd 100knocks-preprocess/`移動して、
```SHELL
$ docker-compose up -d --build
```
* _Cf :_ [Docker入門して機械学習環境構築](https://karaage.hatenadiary.jp/entry/2019/05/17/073000) - からあげ

#### | 🪐Jupyter Lab
```SHELL
$ jupyter lab
```

* _Cf :_ [【データサイエンス】データサイエンス100本ノック！実装までの道程](https://www.youtube.com/watch?v=mh8Z5d0-0PU) - Youtube
* _Cf :_ [Macでデータサイエンス100本ノックを動かす方法](https://qiita.com/karaage0703/items/1b18b1f4ab65d35afb5f)- Qiita
* _Cf :_ [データサイエンス100本ノックを、Google ColabとAzure Notebooksで気軽に行いたい！](https://qiita.com/noguhiro2002/items/de49db61b69c3dbc9282)- Qiita
→環境構築 "怠ッ.." な人向け。コモン化した最強の記事(ありがたい)。


---
## || やってみる

* [Python]()
* [SQL]()
