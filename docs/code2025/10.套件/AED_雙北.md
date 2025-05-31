雙北AED

--Rawdata
```sql
CREATE TABLE aed_locations (
    place_id INTEGER,
    place_name TEXT,
    city TEXT,
    district TEXT,
    address TEXT,
    category TEXT,
    type TEXT,
    description TEXT,
    aed_id INTEGER,
    aed_location TEXT,
    aed_description TEXT,
    lat DOUBLE PRECISION,
    lng DOUBLE PRECISION,
    weekday_open TIME,
    weekday_close TIME,
    saturday_open TIME,
    saturday_close TIME,
    sunday_open TIME,
    sunday_close TIME,
    open_note TEXT,
    emergency_phone TEXT
);
```

components
```sql
INSERT INTO public.components(
	id, index, name)
	VALUES (320, 'aed_locations', 'AED雙北位置資訊');
```

component_chart
```sql
INSERT INTO public.component_charts(
	index, color, types, unit)
	VALUES ('aed_locations', '{#a0b8e8,#b7ff98}', '{DistrictChart,ColumnChart}', '個');
```



query_chart
```sql
INSERT INTO public.query_charts(
    index, history_config, map_config_ids, map_filter, time_from, time_to, update_freq, update_freq_unit,
    source, short_desc, long_desc, use_case, links, contributors, created_at, updated_at,
    query_type, query_chart, query_history, city
)
VALUES (
    'aed_locations', NULL, '{321}', NULL, 'static', NULL, NULL, NULL,
    '交通局交工處', '顯示台北AED', NULL, NULL, NULL, NULL,
    '2025-05-30', '2025-05-30', 'two_d',
    $$



SELECT
  district as x_axis,
  COUNT(*) AS data
FROM
  aed_locations
  where city  in ('臺北市')
GROUP BY
  district
ORDER BY
  data DESC;



$$
    ,
    NULL, 'taipei'
);

```

```sql
INSERT INTO public.query_charts(
    index, history_config, map_config_ids, map_filter, time_from, time_to, update_freq, update_freq_unit,
    source, short_desc, long_desc, use_case, links, contributors, created_at, updated_at,
    query_type, query_chart, query_history, city
)
VALUES (
    'aed_locations', NULL, '{321}', NULL, 'static', NULL, NULL, NULL,
    '交通局交工處', '顯示台北AED', NULL, NULL, NULL, NULL,
    '2025-05-30', '2025-05-30', 'two_d',
    $$



SELECT
  district as x_axis,
  COUNT(*) AS data
FROM
  aed_locations
  where city  in ('新北市','臺北市')
GROUP BY
  district
ORDER BY
  data DESC;

$$
    ,
    NULL, 'metrotaipei'
);

```

map
```sql
INSERT INTO public.component_maps (
	id, index, title, type, source, size, icon, paint, property)
VALUES (
	321,
	'aed_locations',
	'AED位置',
	'symbol',
	'geojson',
	null,
	'youbike',
	'{}'::jsonb,
	'[
	  {"key": "場所名稱", "name": "場所名稱"},
	  {"key": "場所地址", "name": "場所地址"},
	  {"key": "區域代碼", "name": "區域代碼"},
	  {"key": "場所分類", "name": "場所分類"},
	  {"key": "場所類型", "name": "場所類型"},
	  {"key": "AED放置地點", "name": "AED放置地點"},
      {"key": "開放使用時間備註", "name": "開放使用時間備註"},
      {"key": "開放時間緊急連絡電話", "name": "開放時間緊急連絡電話"}
	]'::jsonb
);
```

```sql
INSERT INTO public.component_maps (
	id, index, title, type, source, size, icon, paint, property)
VALUES (
	322,
	'aed_locations',
	'AED位置',
	'symbol',
	'geojson',
	null,
	'youbike',
	'{}'::jsonb,
	'[
  { "key": "場所ID", "name": "場所ID" },
  { "key": "場所名稱", "name": "場所名稱" },
  { "key": "場所縣市", "name": "場所縣市" },
  { "key": "場所區域", "name": "場所區域" },
  { "key": "場所地址", "name": "場所地址" },
  { "key": "場所分類", "name": "場所分類" },
  { "key": "場所類型", "name": "場所類型" },
  { "key": "場所描述", "name": "場所描述" },
  { "key": "AEDID", "name": "AEDID" },
  { "key": "AED放置地點", "name": "AED放置地點" },
  { "key": "AED地點描述", "name": "AED地點描述" },
  { "key": "地點LAT", "name": "地點LAT" },
  { "key": "地點LNG", "name": "地點LNG" },
  { "key": "周一至周五起", "name": "周一至周五起" },
  { "key": "周一至周五迄", "name": "周一至周五迄" },
  { "key": "周六起", "name": "周六起" },
  { "key": "周六迄", "name": "周六迄" },
  { "key": "周日起", "name": "周日起" },
  { "key": "周日迄", "name": "周日迄" },
  { "key": "開放使用時間備註", "name": "開放使用時間備註" },
  { "key": "開放時間緊急連絡電話", "name": "開放時間緊急連絡電話" }
]
'::jsonb
);
```