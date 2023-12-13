---
date   : 2023-12-13
title  : 📍GitHub
excerpt: ブランチのあれこれ操作
tags   : ["📍", "github", "CLI"]
---

## || ブランチとは



## || 作りたい

1. 現在のブランチ状況確認
```shell
$ git branch 
＊ main
```
2. ブランチ作成
```shell 
$ git branch {your branch name}
```
※こっちの方がよく使う。（ブランチ作成してそのブランチに入る）
```shell
$ git checkout -b {your branch name}
```



## || 消したい
### | ブランチ消し方（ファイル指定）
```shell
$ git branch -d {your branch name}
```

### | ブランチ消し方（まとめて）
```shell
$ git branch --merged | egrep -v "(^\*|main|master|develop)" | xargs git branch -d
```
コマンド内容詳細は[reference先](Gitブランチの一括削除!煩雑な作業を一行で解決する方法)へ！



## || REFERENCE
- []() -
- []() -
- []() -
- [Gitブランチの一括削除! 煩雑な作業を一行で解決する方法](https://qiita.com/itinerant_programmer/items/dbf7cdba08a5403234ea) -Qiita
