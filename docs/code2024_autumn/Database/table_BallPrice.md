# 球類價格
```sql
CREATE TABLE TCFData.sports_price (
    id INT AUTO_INCREMENT PRIMARY KEY,
    ball VARCHAR(20),
    price INT
);
INSERT INTO TCFData.sports_price (ball, price) VALUES
('volleyball', 500),
('basketball', 2000),
('badminton', 500),
('table_tennis', 500);
```

