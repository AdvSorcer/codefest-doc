# 球場預約狀態

- **URL**: `/courts_status`
- **方法**: `get`
- **描述**: 所有球場的預約狀態。
- **請求標頭**: 無需認證。

## 請求參數

| 參數        | 類型    | 必填 | 描述                 |
| ----------- | ------- | ---- | -------------------- |
| `category`   | string |    | 球類 volleyball 排球, baseketball籃球,badminton羽球,tabletennis 桌球   |
| `pay`    | Interger   |    |  0:免費 , 1:收費（預設 1）    |
| `district`   | string |    | 行政區  預設給 (全部)   |
| `isBook`   | bool |    | 可以預約    |
| `date`   | string |    | 日期    |
| `period`   | string |    | 時間    |

### 範例請求
```json
{

    "category": "volleyball",
    "pay" : 0,
    "district": "松山區",
    "canbook": true,
    "date": "20240908",
    "period": "09:00-10:00",
}
```

## 回傳
### 回傳範例

```json
[
    {
        "court_id": 85,
        "district": "松山區",
        "name": "松山運動中心",
        "address":"台北市松山區敦化北路1號",
        "date": "20240708",
        "period": "09:00-10:00",
        "reserve_status":true,
        "amount":4 //人數

    },
    {
        "court_id": 86,
        "district": "內湖區",
        "name": "內湖運動中心",
        "address":"台北市內湖區洲子街12號",
        "date": "20240708",
        "period": "09:00-10:00",
        "reserve_status":false,
        "amount":2 //人數
    }
]
```
