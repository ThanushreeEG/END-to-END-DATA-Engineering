# END-to-END-DATA-Engineering



Flow: WeatherAPI → Airbyte → Snowflake → DBT → Analytics/BI


Step-by-Step Pipeline Process
1. Source Configuration (WeatherAPI)
API: WeatherAPI https://www.weatherapi.com/
Endpoint: https://api.weatherapi.com/v1/current.json
API Key: [REDACTED]
Parameter Example: q=India

2. Airbyte Setup
Platform: Airbyte Cloud
Source Connector: HTTP API (GET)
Destination Connector: Snowflake
Sync Frequency: [your cron schedule, e.g., every hour]
Transformation: [none, raw data only]

![image](https://github.com/user-attachments/assets/7f8572c6-e578-4749-906f-300cd03104a6)
![image](https://github.com/user-attachments/assets/7f8572c6-e578-4749-906f-300cd03104a6)

4. Snowflake Configuration
Host: rvzycre-jo72021.snowflakecomputing.com
Database: AIRBYTE_DATABASE
Schema: AIRBYTE_SCHEMA
Warehouse: AIRBYTE_WAREHOUSE
User: AIRBYTE_USER
Role: AIRBYTE_ROLE

5. Sample Data Loaded
Data is loaded into _airbyte_raw_airquality with JSON weather payload.

6. Validation & Troubleshooting
Ensured all connections use HTTPS.
Validated API key and query using curl.
Used Airbyte logs to resolve “no records”/protocol errors.
