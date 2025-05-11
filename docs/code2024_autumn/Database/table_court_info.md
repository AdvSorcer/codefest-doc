```sql
CREATE TABLE TCFData.court_info (
    id INT PRIMARY KEY,
    citycode VARCHAR(255),
    district VARCHAR(255),
    name VARCHAR(255),
    category VARCHAR(255),
    affiliated_agency VARCHAR(255),
    manager_phone VARCHAR(200),
    official_website VARCHAR(255),
    affiliated_property VARCHAR(200),
    address VARCHAR(255),
    facilities VARCHAR(255),
    availability_status VARCHAR(255),
    opening_days VARCHAR(255),
    pay_use VARCHAR (255),
    opening_closure_notice TEXT,
    parking_type VARCHAR(255),
    venue_description TEXT
);
```

sudo docker cp /home/morgan/sp4.csv ubuntu-server:/var/lib/mysql-files/
