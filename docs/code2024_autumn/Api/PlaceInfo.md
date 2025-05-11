# 球場資訊

- **URL**: `/api/courts`
- **方法**: `get`
- **描述**: 所有球場的資訊(列表用）。
- **請求標頭**: 無需認證。

## 請求參數

| 參數        | 類型    | 必填 | 描述                 |
| ----------- | ------- | ---- | -------------------- |
| `category`   | string |    | volleyball (排球), baseketball 籃球,badminton羽球,tabletennis 桌球   |
| `pay`    | Interger   |    |  0:免費 , 1:收費    |
| `district`   | string |    | 行政區    |


### 範例請求

```json
{

    "category": "volleyball",
    "pay" : 0,
    "district": "松山區",
}
```





## 回傳

| 參數                       | 類型    | 必填 | 描述                                      |
| -------------------------- | ------- | ---- | ----------------------------------------- |
| `court_id`                 | Integer |    | 場館的唯一識別碼                          |
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


### 回傳範例

```json
[
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
        "venue_description": "場地包括籃球場一面兼排球場一面，亦可進行瑜伽課程及有氧舞蹈課程，同時可供校內外各類運動競賽舉辦用。"
    }, 
    {
        "id": 2,
        "district": "台北市內湖區",
        "name": "內湖運動中心",
        "category": "運動中心",
        "affiliated_agency": "台北市政府",
        "manager_phone": "02 2656 2869",
        "official_website": "https://nhsc.cyc.org.tw/",
        "affiliated_property": "公立",
        "address": "台北市內湖區洲子街12號",
        "facilities": "排球場(館)",
        "availability_status": "付費對外開放使用",
        "opening_days": "一二三四五六日",
        "opening_closure_notice": "除寒暑假外，休假日及國定假日開放，平日上課期間，不對外開放。",
        "parking_type": "一般及無障礙停車場",
        "venue_description": "場地包括籃球場一面兼排球場一面，亦可進行瑜伽課程及有氧舞蹈課程，同時可供校內外各類運動競賽舉辦用。"
    }
]
```

### 後端邏輯
時間要修改
- 一二三四五六日 --> 每週一至週日
- 六日 -->  每週六和日
- 一二三四五 --> 每週一至週五
- 一二三四 --> 每週一至週四
- 二四六日 --> 每週二、四、六和日
- 六 -->  每週六
- 二四六 --> 每週二、四和六



> 行政區	場館名稱	場館分類	場館隸屬機關		場館實際管理人電話	場館官方網站	場館隸屬機關屬性	地址			設施項目	開放情形	開放時間	租借資訊	開放及休館時間補充說明	停車場種類	運動場館介紹