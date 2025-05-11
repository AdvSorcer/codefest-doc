# 揪團預約

- **URL**: `/book_court`
- **方法**: `POST`
- **描述**: 預約球場
- **請求標頭**: 無需認證。
- **請求參數**:
  | 參數          | 類型   | 必填 | 描述           |
  | ------------- | ------ | ---- | -------------- |
  | `id_type`    | String | 是   | 使用者名稱     |
  | `court_id`   | String | 是   | 球場id     |
  | `date`    | String | 是   | 日期     |
  | `time`    | String | 是   | 時段     |

- 請求:
```json
  {
    "user_id": "morgan/身份id",
    "court_id": 97,
    "date": "20240724" ,
    "time" : "09:00-10:00"
  }
```

## 回傳

  | 參數          | 類型   | 必填 | 描述           |
  | ------------- | ------ | ---- | -------------- |
  | `id_type`    | String | 是   | 狀態     |
  | `message`    | String | 是   | 訊息     |
  | `date`    | String | 是   | 日期     |
  | `time`    | String | 是   | 時間     |
  | `court_name`    | String | 是   | 場館     |

### 成功
```json
{
  "status": "success",
  "message": "預約成功",
  "date": "20240724" ,
  "time" : "09:00-10:00",
  "court_name" : "台大體育館-籃球場1"
}
```

### 失敗(Not Use)
```json
{
  "status": "fail",
  "message": "預約失敗，人數已滿",
}
```