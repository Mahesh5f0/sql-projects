# 🌦️ Weather Database Project  

This project is a **Weather Dataset Analysis** using SQL queries. The dataset contains different weather parameters like temperature, humidity, wind speed, visibility, atmospheric pressure, and weather conditions.  
The main objective is to practice SQL queries to extract meaningful insights from the dataset.  


## 📂 Dataset Details  
The dataset contains **8 columns**:  - [Weather Database Link](https://drive.google.com/file/d/1JKDv4C1_jXYmbqki2z9yVlYMV3pRaDgD/view?usp=drive_link)  

| Column Name            | Description |
|-------------------------|-------------|
| Date/Time              | Timestamp of weather record (MM/DD/YYYY HH:MM) |
| Temp_C                 | Temperature in °C |
| Dew Point Temp_C       | Dew point temperature in °C |
| Rel Humidity           | Moisture in the air (%) |
| Wind Speed (km/h)      | Wind speed in km/h |
| Visibility (km)        | Visibility in kilometers |
| Pressure (kPa)         | Atmospheric pressure in kilopascals |
| Weather                | Weather condition |


## 📝 Weather Data SQL Queries & Analysis  

A collection of useful SQL queries for analyzing weather data. Each query follows the format: **SQL statement** plus the **Result**.

### 1. Maximum Temperature Recorded - [Result](https://drive.google.com/file/d/1H7KwyWAs9kVMPA2II4y2V-XBYjanpAVU/view?usp=drive_link)  
```sql
SELECT MAX(Temp_C) AS max_temperature FROM weather;
```
  
### 2. Distinct Weather Conditions - [Result](https://drive.google.com/file/d/1wc4AzDBKwVa8qt967_S8N2526PQrwfJ9/view?usp=drive_link%20)  
```sql
SELECT DISTINCT weather FROM weather;;
```

### 3. Foggy Hours - [Result](https://drive.google.com/file/d/1HM8SH7RG7mxtP7sqp39yZzWCd716vEs6/view?usp=drive_link%20)  
```sql
SELECT COUNT(*) AS foggy_hours FROM weather
WHERE weather LIKE '%fog%';
```

### 4. Average Temperature by Weather Condition - [Result](https://drive.google.com/file/d/1vfzBNULIqjf60iqPlZv9X5wPcIkvZdNi/view?usp=drive_link)  
```sql
SELECT weather, AVG(temp_c) AS avg_temperature FROM weather
GROUP BY weather
ORDER BY avg_temperature DESC;
```

### 5. Hours with Visibility Below 1km - [Result](https://drive.google.com/file/d/1feRHKv1Eo_Um4yam_OIwtcx_MJHRME09/view?usp=drive_link)  
```sql
SELECT COUNT(*) AS low_visibility_hours FROM weather
WHERE visibility_km < 1;
```

### 6. Average Pressure When Temperature Below 0°C - [Result](https://drive.google.com/file/d/1kKpw3yciPzWRx0t6BfcZADMXn80w3p2k/view?usp=drive_link)  
```sql
SELECT AVG(press_kpa) AS avg_pressure FROM weather
WHERE temp_c < 0;
```

### 7. Rainy Hours - [Result](https://drive.google.com/file/d/1z_ZHRUGn8evkmL5ztmSXX0TADRgs2wAm/view?usp=drive_link)  
```sql
SELECT COUNT(*) AS rainy_hours FROM weather
WHERE weather LIKE '%Rain%';
```

### 8. Top 5 Most Frequent Weather Conditions - [Result](https://drive.google.com/file/d/1GqduutPxkxM4OY6VemvoeG_VRAvmB9kx/view?usp=drive_link)  
```sql
SELECT weather, COUNT(*) AS frequency FROM weather
GROUP BY weather
ORDER BY frequency DESC
LIMIT 5;
```

### 9. Average Visibility During Foggy Weather - [Result](https://drive.google.com/file/d/111N5Q8uvoud3OrabBQ6PgeYZtlYgqxzH/view?usp=drive_link)  
```sql
SELECT AVG(visibility_km) AS avg_visibility FROM weather
WHERE weather LIKE '%fog%';
```


### 10. Maximum Dew Point Recorded and When It Occurred - [Result](https://drive.google.com/file/d/1KW-Z09gHF7w2l-TrNReoO40n9lrgSX3a/view?usp=drive_link)  
```sql
SELECT date_time, dew_point_temp_c FROM weather
ORDER BY dew_point_temp_c DESC
LIMIT 1;
```

### 11. Average Wind Speed for Each Weather Condition - [Result](https://drive.google.com/file/d/11L9-eBbWlW-rrTWdnLmL7yMIxaBRKU4n/view?usp=drive_link)  
```sql
SELECT weather, AVG(wind_speed_km_h) AS avg_windspeed FROM weather
GROUP BY weather
ORDER BY avg_windspeed DESC;
```


## 👨‍💻 Author
**Mahesh Poleboina**  
B.Tech – Computer Science & Engineering (2025)  
Tirumala Engineering College  

---





