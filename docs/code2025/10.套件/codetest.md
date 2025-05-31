# codetest

```sql
INSERT INTO public.query_charts(
    index, history_config, map_config_ids, map_filter, time_from, time_to, update_freq, update_freq_unit,
    source, short_desc, long_desc, use_case, links, contributors, created_at, updated_at,
    query_type, query_chart, query_history, city
)
VALUES (
    'car_crash_point', NULL, NULL, NULL, 'static', NULL, NULL, NULL, '交通局交工處', '顯示雙北當前車禍', NULL, NULL, NULL, NULL,
    '2025-05-30', '2025-05-30', 'two_d',
    $$
    SELECT left(location,3) AS x_axis, count(*) AS data
    FROM public.car_crash_point
    GROUP BY left(location,3)
    HAVING count(*) > 50
    ORDER BY CASE left(location,3)
        WHEN '北投區' THEN 1
        WHEN '士林區' THEN 2
        WHEN '內湖區' THEN 3
        WHEN '南港區' THEN 4
        WHEN '松山區' THEN 5
        WHEN '信義區' THEN 6
        WHEN '中山區' THEN 7
        WHEN '大同區' THEN 8
        WHEN '中正區' THEN 9
        WHEN '萬華區' THEN 10
        WHEN '大安區' THEN 11
        WHEN '文山區' THEN 12
        WHEN '新莊區' THEN 13
        WHEN '淡水區' THEN 14
        WHEN '汐止區' THEN 15
        WHEN '板橋區' THEN 16
        WHEN '三重區' THEN 17
        WHEN '樹林區' THEN 18
        WHEN '土城區' THEN 19
        WHEN '蘆洲區' THEN 20
        WHEN '中和區' THEN 21
        WHEN '永和區' THEN 22
        WHEN '新店區' THEN 23
        WHEN '鶯歌區' THEN 24
        WHEN '三峽區' THEN 25
        WHEN '瑞芳區' THEN 26
        WHEN '五股區' THEN 27
        WHEN '泰山區' THEN 28
        WHEN '林口區' THEN 29
        WHEN '深坑區' THEN 30
        WHEN '石碇區' THEN 31
        WHEN '坪林區' THEN 32
        WHEN '三芝區' THEN 33
        WHEN '石門區' THEN 34
        WHEN '八里區' THEN 35
        WHEN '平溪區' THEN 36
        WHEN '雙溪區' THEN 37
        WHEN '貢寮區' THEN 38
        WHEN '金山區' THEN 39
        WHEN '萬里區' THEN 40
        WHEN '烏來區' THEN 41
        ELSE 999
    END
    $$,
    NULL, 'taipei'
); 
```

```sql
INSERT INTO public.component_maps (
    id, index, title, type, source, size, icon, paint, property
) VALUES (
    300,
    'car_crash_point',
    '車禍網圖',
    'symbol',
    'geojson',
    null,
    null,
    '{}'::jsonb,
    '[
        {"key":"sna", "name":"場站名稱"},
        {"key":"sno", "name":"場站ID"},
        {"key":"available_return_bikes", "name":"可還車位"},
        {"key":"available_rent_general_bikes", "name":"剩餘車輛"}
    ]'::jsonb
);
```