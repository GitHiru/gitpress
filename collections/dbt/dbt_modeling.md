---
date    : 2023-12-06
title   : ✴️ dbt
excerpt : モデル作成とモデル機能
tags    : ["✴️", "dbt", "ETL/ELT", "MDS"]
---

![image](https://github.com/sh16ma/gitpress/assets/150888300/d3b2fdbc-417f-4145-8f6b-d9e2ab58c483)

## || モデリング
### | データソースの準備
```shell
# PostgreSQLログイン
(venv)$ psql -U postgres # PostgreSQLログイン
postgres=#
# データベース（DB）作成
postgres=# \d # DB一覧確認
postgres=# CREATE DATABASE dbt_training; #
# テーブル作成
postgres=# \cd dbt_training # 作成したDBに移動
dbt_training=# CREATE SCHEMA raw; # スキーマ作成
dbt_training=# \du # ロール一覧確認
    List of schemas　
　Name      |  Owner
------------+----------
　public    | postgres
　raw       | postgres
    (2 rows)
# 各種テーブル作成
dbt_training=# 
-- 従業員テーブル
CREATE TABLE "dbt_training"."raw"."employees" (
	"employee_id" varchar(256),
	"first_name" varchar(256),
	"last_name" varchar(256),
	"email" varchar(256),
	"job_id" varchar(256),
	"loaded_at" timestamp
);
dbt_training=# 
-- お仕事テーブル
CREATE TABLE "dbt_training"."raw"."jobs" (
	"job_id" varchar(256),
	"job_title" varchar(256),
	"min_salary" INTEGER,
	"max_salary" INTEGER,
	"loaded_at" timestamp
);
dbt_training=# \dt myschema.* # スキーマ内テーブル一覧確認
# データ格納
dbt_training=# 
-- 従業員テーブルへデータをINSERT
INSERT INTO "dbt_training"."raw"."employees" VALUES
	('101','taro','yamada','yamada@example.com','11','2022-03-16'),
	('102','ziro','sato','satou@example.com','11','2022-03-16')
;
dbt_training=# 
-- お仕事テーブルへデータをINSERT
INSERT INTO "dbt_training"."raw"."jobs" VALUES
	('11','datascientist',6000000,12000000,'2022-03-16'),
	('12','dataengineer',5000000,10000000,'2022-03-16')
;
# PostgreSQLログアウト
dbt_training=# \q
postgres=# \q
```
🐘[PostgreSQL](https://gitpress.io/c/postgresql/sql_postgre)のコマンド参照。

### | モデル作成

```shell
(venv)$ touch models/employee_names.sql)
```

```sql
select
	"employee_id"
	, concat("first_name", ' ', "last_name") as full_name
from
	"dbt_training"."raw"."employees"
```

```shell
(venv)$ dbt run 
```

### | マテリアライゼーション

|種類|説明|
|:-|:-|
|view||
|table||
|incremental||
|ephemeral||



## || REFERENCE 
- [モデルを作ろう](https://zenn.dev/foursue/books/31456a86de5bb4/viewer/6037e5) -Zenn
- [SQL models](https://docs.getdbt.com/docs/build/sql-models) -dbt official
- [Materializations](https://docs.getdbt.com/docs/build/materializations) -dbt official
- [Incremental models](https://docs.getdbt.com/docs/build/incremental-models) -dbt official
-
