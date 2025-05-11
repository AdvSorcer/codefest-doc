# 球場資訊

- **URL**: `/api/court_one`
- **方法**: `get`
- **描述**: 單一球場的資訊(內頁用）。
- **請求標頭**: 無需認證。

## 請求參數

| 參數        | 類型    | 必填 | 描述                 |
| ----------- | ------- | ---- | -------------------- |
| `court_id`   | int |    |  場館的唯一識別碼    |



### 範例請求

```json
{
    "court_id":87
}
```


## 回傳

| 參數                       | 類型    | 必填 | 描述                                      |
| -------------------------- | ------- | ---- | ----------------------------------------- |
| `court_id`                       | Integer |    | 場館的唯一識別碼                          |
| `district`                 | String  |    | 行政區名稱                                |
| `name`                     | String  |    | 場館名稱                                  |
| `category`                 | String  |    | 場館分類（如籃球場、羽球場等）            |
| `affiliated_agency`        | String  |    | 場館隸屬機關                              |
| `manager_phone`            | String  |    | 場館實際管理人的電話                      |
| `official_website`         | String  |    | 場館官方網站網址                          |
| `affiliated_property`      | String  |    | 場館隸屬機關的屬性       |
| `address`                  | String  |    | 場館詳細地址                              |
| `facilities`               | String  |    | 場館內的設施項目    |
| `availability_status`      | String  |   | 開放說明                              |
| `opening_days`            | String  |    | 場館的開放時間                            |
| `opening_closure_notice`   | String  |    | 開放及休館時間的補充說明                  |
| `parking_type`             | String  |    | 停車場種類（如室內停車場、戶外停車場等） |
| `venue_description`        | String  |    | 場館簡介                                  |
| `price`        | int  |    | 價格                                  |



### 回傳範例

```json

        {
        "id": 1,
        "district": "台北市松山區",
        "name": "松山運動中心",
        "category": "運動中心",
        "affiliated_agency": "台北市政府",
        "manager_phone": "02 7755 5058",
        "official_website": "https://sssc.com.tw/",
        "affiliated_property": "公立",
        "address": "台北市松山區敦化北路1號",
        "facilities": "排球場(館)",
        "availability_status": "付費對外開放使用",
        "opening_days": "一二三四五六日",
        "opening_closure_notice": "除寒暑假外，休假日及國定假日開放，平日上課期間，不對外開放。",
        "parking_type": "一般及無障礙停車場",
        "venue_description": "場地包括籃球場一面兼排球場一面，亦可進行瑜伽課程及有氧舞蹈課程，同時可供校內外各類運動競賽舉辦用。",
        "price":500
    }

```

### 取得資料
```sql
SELECT * FROM TCFData.court_info where id=87;
```

### 取得價格
```sql
select * from TCFData.sports_price where ball = 'basketball'
```
