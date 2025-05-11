# 發送預約信件


- **URL**: `/send_book_mail`
- **方法**: `post`
- **描述**: 寄送成功預約訊息
- **請求標頭**: 無需認證。

## 說明
此為內部系統 API 呼叫，由預約 API 發起，非供外部使用

## 請求
```json
{
  "user_name": "黃台北",
  "court_name": "內湖運動中心",
  "datetime": "2024-09-08 10:00:00"
}
```

## 回應
```json
{
  "status": "success",
  "message":"發送成功"
}
```