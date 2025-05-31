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