---
date    : 2021-09-25
title   : 【🔎 SQL】データサイエンス100本ノック（構造化データ加工編）
excerpt : データサイエンス協会が、データサイエンス初学者のための実践的な学習環境をGitHubに無料公開！
tags    : ["DataScientist", "GitHub", "Docker", "SQL"]
---
## SQL編
### | S-001
レシート明細テーブル(receipt)から全項目を10件抽出し、どのようなデータを保有して いるか目視で確認せよ。
```SQL
select * from `100knocks.receipt` limit 10;
```

### | S-002
レシート明細のテーブル(receipt)から売上日(sales_ymd)、顧客ID (customer_id)、商品コード(product_cd)、売上金額(amount)の順に列を指定し、 10件表示させよ。
```SQL
select
    sales_ymd
    , customer_id
    , product_cd
    , amount
from `100knocks.receipt`
limit 10
;
```

### |S-003
レシート明細のテーブル(receipt)から売上日(sales_ymd)、顧客ID (customer_id)、商品コード(product_cd)、売上金額(amount)の順に列を指定し、10件表示させよ。ただし、sales_ymdはsales_dateに項目名を変更しながら抽出するこ と。
```SQL
select
    sales_ymd as sales_date
    , customer_id
    , product_cd
    , amount
from `100knocks.receipt`
limit 10
;
```

### | S-004
レシート明細のテーブル(receipt)から売上日(sales_ymd)、顧客ID (customer_id)、商品コード(product_cd)、売上金額(amount)の順に列を指定し、 以下の条件を満たすデータを抽出せよ。
+ 顧客ID（customer_id）が"CS018205000001"

```SQL
select
    sales_ymd
    , customer_id
    , product_cd
    , amount
from `100knocks.receipt`
where customer_id = 'CS018205000001'
;
```

### | S-005
レシート明細のテーブル(receipt)から売上日(sales_ymd)、顧客ID (customer_id)、商品コード(product_cd)、売上金額(amount)の順に列を指定し、 以下の条件を満たすデータを抽出せよ。
+ 顧客ID（customer_id）が"CS018205000001"
+ 売上金額（amount）が1,000以上

```sql
select
    sales_ymd
    , customer_id
    , product_cd
    , amount
from `100knocks.receipt`
where
    customer_id = 'CS018205000001'
    and
    amount >= 1000
;
```

### | S-006
レシート明細テーブル(receipt)から売上日(sales_ymd)、顧客ID(customer_id)、 商品コード(product_cd)、売上数量(quantity)、売上金額(amount)の順に列を指定 し、以下の条件を満たすデータを抽出せよ。
+ 顧客ID（customer_id）が"CS018205000001"
+ 売上金額（amount）が1,000以上または売上数量（quantity）が5以上

```sql
select
    sales_ymd
    , customer_id
    , product_cd
    , quantity
    , amount
from `100knocks.receipt`
where
    customer_id = 'CS018205000001'
    and
    (amount >= 1000 or quantity >= 5)
;
```

### | S-007
レシート明細のテーブル(receipt)から売上日(sales_ymd)、顧客ID (customer_id)、商品コード(product_cd)、売上金額(amount)の順に列を指定し、 以下の条件を満たすデータを抽出せよ。
+ 顧客ID（customer_id）が"CS018205000001"
+ 売上金額（amount）が1,000以上2,000以下

```sql
select
    sales_ymd
    , customer_id
    , product_cd
    , amount
from `100knocks.receipt`
where
    customer_id = 'CS018205000001'
    and
    amount between 1000 and 2000
;
```

### | S-008
レシート明細テーブル(receipt)から売上日(sales_ymd)、顧客ID(customer_id)、 商品コード(product_cd)、売上金額(amount)の順に列を指定し、以下の条件を満た すデータを抽出せよ。
+ 顧客ID（customer_id）が"CS018205000001"
+ 商品コード（product_cd）が"P071401019"以外

```SQL
select
    sales_ymd
    , customer_id
    , product_cd
    , amount
from `100knocks.receipt`
where
    customer_id = 'CS018205000001'
    and
    product_cd <> 'P071401019'
;
```

### | S-009
以下の処理において、出力結果を変えずにORをANDに書き換えよ。

`select * from store where not (prefecture_cd = '13' or floor_area > 900)`

```sql
select
    *
from `100knocks.store`
where
    prefecture_cd <> 13
    and
    floor_area < 900
;
```

### | S-010
店舗テーブル(store)から、店舗コード(store_cd)が"S14"で始まるものだけ全項目抽 出し、10件だけ表示せよ。

```SQL
select
    *
from `100knocks.store`
where store_cd like 'S14%'
-- where regexp_contains(store_cd, r'S14') #別解
limit 10
;
```

### | S-011
顧客テーブル(customer)から顧客ID(customer_id)の末尾が1のものだけ全項目抽出 し、10件だけ表示せよ。

```SQL
select
    *
from `100knocks.customer`
where regexp_contains(customer_id, r'1$')
limit 10
;
```

### | S-012
店舗テーブル(store)から横浜市の店舗だけ全項目表示せよ。
```SQL
select
    *
from `100knocks.store`
where address like '%横浜市%'
;
```

### | S-013
顧客テーブル(customer)から、ステータスコード(status_cd)の先頭がアルファベッ トのA〜Fで始まるデータを全項目抽出し、10件だけ表示せよ。
```SQL
select
    *
from `100knocks.customer`
where
    regexp_contains(customer_id, r'^(A|B|C|D|E|F)')
    -- customer_id like 'A%'
    -- or
    -- customer_id like 'B%'
    -- or
    -- customer_id like 'C%'
    -- or
    -- customer_id like 'D%'
    -- or
    -- customer_id like 'E%'
    -- or
    -- customer_id like 'F%'
limit 10
;
```
Cf. [BigQueryでLIKE文の複数条件指定をORから正規表現に直す](https://qiita.com/mida12251141/items/27fe42ef01e83d5b063f) - Qiita

### | S-014
顧客テーブル(customer)から、ステータスコード(status_cd)の末尾が数字の1〜9で 終わるデータを全項目抽出し、10件だけ表示せよ。
```SQL
select
    *
from `prj-test3.100knocks.customer`
where
    regexp_contains(status_cd, r'[1-9]$')
limit 10
;
```

### | S-015
顧客テーブル(customer)から、ステータスコード(status_cd)の先頭がアルファベットのA〜Fで始まり、末尾が数字の1〜9で終わるデータを全項目抽出し、10件だけ表示せよ。
```SQL
select
    *
from `prj-test3.100knocks.customer`
where
    regexp_contains(status_cd, r'^(A|B|C|D|E|F)-\d+-[1-9]$')
limit 10
;
```
Cf. [基本的な正規表現一覧](https://murashun.jp/article/programming/regular-expression.html) - murashun.jp

### | S-016
店舗テーブル(store)から、電話番号(tel_no)が3桁-3桁-4桁のデータを全項目表示せよ。
```SQL
select
    *
from `prj-test3.100knocks.store`
where regexp_contains(tel_no, r'\d{3}-\d{3}-\d{4}')
;
```

### | S-017
顧客テーブル(customer)を生年月日(birth_day)で高齢順にソートし、先頭10件を全項目表示せよ。
```SQL
```

### | S-018
顧客テーブル(customer)を生年月日(birth_day)で若い順にソートし、先頭10件を全 項目表示せよ。
```SQL
```

### | S-019
レシート明細テーブル(receipt)に対し、1件あたりの売上金額(amount)が高い順にラ ンクを付与し、先頭10件を抽出せよ。項目は顧客ID(customer_id)、売上金額 (amount)、付与したランクを表示させること。なお、売上金額(amount)が等しい場合は同一順位を付与するものとする。
```SQL
```

### | S-020
レシート明細テーブル(receipt)に対し、1件あたりの売上金額(amount)が高い順にラ ンクを付与し、先頭10件を抽出せよ。項目は顧客ID(customer_id)、売上金額 (amount)、付与したランクを表示させること。なお、売上金額(amount)が等しい場 合でも別順位を付与すること。
```SQL
```

### | S-021
レシート明細テーブル(receipt)に対し、件数をカウントせよ。
```SQL
```

### | S-022
レシート明細テーブル(receipt)の顧客ID(customer_id)に対し、ユニーク件数をカウ ントせよ。
```SQL
```

### | S-023
レシート明細テーブル(receipt)に対し、店舗コード(store_cd)ごとに売上金額 (amount)と売上数量(quantity)を合計せよ。
```SQL
```

### | S-024
レシート明細テーブル(receipt)に対し、顧客ID(customer_id)ごとに最も新しい売上 日(sales_ymd)を求め、10件表示せよ。
```SQL
```

### | S-025
レシート明細テーブル(receipt)に対し、顧客ID(customer_id)ごとに最も古い売上日 (sales_ymd)を求め、10件表示せよ。
```SQL
```

### | S-026
レシート明細テーブル(receipt)に対し、顧客ID(customer_id)ごとに最も新しい売上 日(sales_ymd)と古い売上日を求め、両者が異なるデータを10件表示せよ。
```SQL
```

### | S-027
レシート明細テーブル(receipt)に対し、店舗コード(store_cd)ごとに売上金額 (amount)の平均を計算し、降順でTOP5を表示せよ。
```SQL
```

### | S-028
レシート明細テーブル(receipt)に対し、店舗コード(store_cd)ごとに売上金額 (amount)の中央値を計算し、降順でTOP5を表示せよ。
```SQL
```

### | S-029
レシート明細テーブル(receipt)に対し、店舗コード(store_cd)ごとに商品コード (product_cd)の最頻値を求めよ。
```SQL
```

### | S-030
```SQL
```

### | S-031
```SQL
```

### | S-032
```SQL
```

### | S-033
```SQL
```

### | S-034
```SQL
```

### | S-035
```SQL
```

### | S-036
```SQL
```

### | S-037
```SQL
```

### | S-038
```SQL
```

### | S-039
```SQL
```

### | S-040
```SQL
```

### | S-041
```SQL
```

### | S-042
```SQL
```

### | S-043
```SQL
```

### | S-044
```SQL
```

### | S-045
```SQL
```

### | S-045
```SQL
```

### | S-046
```SQL
```

### | S-047
```SQL
```

### | S-048
```SQL
```

### | S-049
```SQL
```

### | S-050
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```

### | S-0
```SQL
```
