component
```sql
INSERT INTO public.components(
	id, index, name)
	VALUES (800, 'AED', 'AED資訊');
```

component_chart
```sql
INSERT INTO public.component_charts(
	index, color, types, unit)
	VALUES ('AED', '{#a0b8e8,#b7ff98}', '{DistrictChart,ColumnChart}', '個');
```

map
```sql
INSERT INTO public.component_maps (
	id, index, title, type, source, size, icon, paint, property)
VALUES (
	822,
	'AED',
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
	  {"key": "AED放置地點", "name": "AED放置地點"}
	]'::jsonb
);
```

query_chart
```sql
INSERT INTO public.query_charts(
    index, history_config, map_config_ids, map_filter, time_from, time_to, update_freq, update_freq_unit,
    source, short_desc, long_desc, use_case, links, contributors, created_at, updated_at,
    query_type, query_chart, query_history, city
)
VALUES (
    'AED', NULL, '{822}', NULL, 'static', NULL, NULL, NULL,
    '交通局交工處', '顯示台北AED', NULL, NULL, NULL, NULL,
    '2025-05-30', '2025-05-30', 'two_d',''
    ,
    NULL, 'taipei'
);

```

