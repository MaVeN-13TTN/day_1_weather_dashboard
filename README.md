# 30 Days DevOps Challenge - Weather Dashboard

Day 1: Building a weather data collection system using AWS S3 and OpenWeather API

# Weather Data Collection System - DevOps Day 1 Challenge

## Project Overview
This project is a Weather Data Collection System that demonstrates core DevOps principles by combining:
- External API Integration (OpenWeather API)
- Cloud Storage (AWS S3)
- Infrastructure as Code
- Version Control (Git)
- Python Development
- Error Handling
- Environment Management

## Features
- Fetches real-time weather data for multiple cities
- Displays temperature (°F), humidity, and weather conditions
- Automatically stores weather data in AWS S3 with timestamps
- Supports multiple cities tracking
- Uses random bucket names for unique storage
- Timestamps all data for historical tracking

## Technical Architecture
- **Language:** Python 3.x
- **Cloud Provider:** AWS (S3)
- **External API:** OpenWeather API
- **Dependencies:** 
  - boto3 (AWS SDK)
  - python-dotenv
  - requests

## Project Structure
```
weather-dashboard/
  src/
    __init__.py
    weather_dashboard.py
  tests/
  data/
  .env
  .env.example
  .gitignore
  requirements.txt
```

## Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/MaVeN-13TTN/day_1_weather_dashboard.git
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Configure environment variables:
   - Copy `.env.example` to `.env`
   - Update the values in `.env`:
```ini
# OpenWeather API Configuration
OPENWEATHER_API_KEY=your_api_key_here

# AWS S3 bucket configuration
AWS_BUCKET_NAME=weather-data
```

4. Configure AWS credentials:
```bash
aws configure
```
This will prompt you to enter:
- AWS Access Key ID
- AWS Secret Access Key
- Default region (e.g., us-east-1)
- Default output format

5. Run the application:
```bash
python src/weather_dashboard.py
```

## How It Works

1. **Environment Setup**
   - Loads configuration from `.env` file
   - Uses AWS credentials from `aws configure`

2. **Bucket Creation**
   - Creates a unique S3 bucket using the format: `weather-data-[random-number]`
   - Random number ensures unique bucket names for each run

3. **Weather Data Collection**
   - Fetches weather data for Philadelphia, Seattle, and New York
   - Displays current conditions including:
     - Temperature (°F)
     - Feels like temperature
     - Humidity percentage
     - Weather conditions

4. **Data Storage**
   - Saves weather data as JSON files in S3
   - Uses timestamp-based naming: `weather-data/[city]-[timestamp].json`
   - Includes metadata for historical tracking

## What I Learned
- AWS S3 bucket creation and management
- Environment variable management for secure API keys
- Python best practices for API integration
- Error handling and logging
- AWS credential management using `aws configure`

## Future Enhancements

- Add weather forecasting
- Implement data visualization
- Add more cities
- Create automated testing
- Set up CI/CD pipeline
