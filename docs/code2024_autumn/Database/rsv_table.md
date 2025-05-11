# 預約紀錄表 
```sql
CREATE TABLE RSV_20240908 (
    ID INT AUTO_INCREMENT PRIMARY KEY, -- 流水號，自增主鍵
    userId VARCHAR(100) NOT NULL, -- 使用者名稱
    court_id VARCHAR(30) NOT NULL, -- 球場ID
    period VARCHAR(30) NOT NULL, -- 時段
    create_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP -- 創建時間，預設為當前時間
);
```