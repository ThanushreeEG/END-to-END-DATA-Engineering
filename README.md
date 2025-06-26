# END-to-END-DATA-Engineering



Flow: WeatherAPI → Airbyte → Snowflake → DBT → Analytics/BI


Step-by-Step Pipeline Process
1. Source Configuration (WeatherAPI)
API: WeatherAPI https://www.weatherapi.com/
Endpoint: https://api.weatherapi.com/v1/current.json
API Key: [REDACTED]
Parameter Example: q=India
![image](https://github.com/user-attachments/assets/0f860613-69fb-4214-ae60-cc18a956c73e)


3. Airbyte Setup
Platform: Airbyte Cloud
Source Connector: HTTP API (GET)
Destination Connector: Snowflake
Sync Frequency: [your cron schedule, e.g., every hour]
Transformation: [none, raw data only]

![image](https://github.com/user-attachments/assets/7f8572c6-e578-4749-906f-300cd03104a6)

4. Snowflake Configuration
Host: rvzycre-jo72021.snowflakecomputing.com
Database: AIRBYTE_DATABASE
Schema: AIRBYTE_SCHEMA
Warehouse: AIRBYTE_WAREHOUSE
User: AIRBYTE_USER
Role: AIRBYTE_ROLE
![image](https://github.com/user-attachments/assets/04818582-a902-44d9-963e-ce1a5f732f8f)


6. Sample Data Loaded
Data is loaded into _airbyte_raw_airquality with JSON weather payload.

![image](https://github.com/user-attachments/assets/de9708d9-d25a-4e1d-83b3-1bf4f20ed644)

7. Validation & Troubleshooting
Ensured all connections use HTTPS.
Validated API key and query using curl.
Used Airbyte logs to resolve “no records”/protocol errors.
