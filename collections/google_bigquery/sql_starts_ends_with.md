---
date    : 2024-01-17
title   : 🔍 starts_with・ends_with関数
excerpt : 文頭、文尾の判定
tags    : ["🔍", "BigQuery", "GoogleCloud"]
---

## || [STARTS|ENDS]_WITH()
### | こんな感じ
```SQL
with 
    fruits as (
        select "apple" as item 
        union all
        select "banana" as item
        union all
        select "orange" as item
    )
select 
    item
    , ends_with(item, "e") as is_included
from fruits
/*
= 末尾に「e」が含まれているか？
|item  |is_included|
|apple |True       |
|banana|False      |
|orange|True       |
*/
```

### | 使い処
e.g. 社用での規定アドレスに含まれているか否か
```SQL
-- UDFは割愛しているのでundifind columnありに注意（あくまでサンプルクエリ）
select
    creation_time
    , job_id
    , project_id
    , user_email
    , round(safe_divide(total_slot_ms, 1000 * 60 * 60 * 24), 1) as total_slot_day
    , round(safe_divide(total_slot_ms, 1000 * 60 * 60 * 24) * (1700 / 100 / 30), 1) as approx_slot_cost
    , destination_table
from `region-us.INFORMATION_SCHEMA.JOBS_BY_ORGANIZATION`
where 
    datetime(creation_time, 'Asia/Tokyo') between start_datetime and end_datetime
    and safe_divide(total_slot_ms, 1000 * 60 * 60 * 24) >= total_slot_day_threshold
    and (ends_with(user_email, 'gserviceaccount.com') is false and user_email not like '%looker%') -- 個人アカウント
    and statement_type != 'SCRIPT' --SCRIPT を除く
    and starts_with(project_id, 'company-us-') is false --us を除く
```


## || REFERENCE
- [ENDS_WITH function in Bigquery - SQL Syntax and Examples](https://roboquery.com/app/syntax-ends-with-function-bigquery) -　Roboquery
- []() - 