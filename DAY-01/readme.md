# 🌦️ Building a Weather Data Collection System with AWS S3 and OpenWeather API 🌍

Hello, tech enthusiasts! 👋 Welcome to my blog, where I share my experiences and insights from the #DevOpsAllStarsChallenge 🚀. Today, I’m excited to walk you through an interesting project I recently worked on: **Building a Weather Data Collection System**.  

This system fetches real-time weather data 🌡️ from the OpenWeather API and stores it in an AWS S3 bucket 🪣 as JSON files. Along the way, I explored API integration, cloud storage management, version control with Git, and Python programming 🐍. It was a hands-on learning experience that pushed me to think outside the box and solve some interesting challenges.

Let’s dive into how I made this work, step by step! 👇


![alt text](image.png)

---

## 🛠️ Prerequisites

Before starting, I ensured I had the following resources:  

### Resources:
- 🌐 Basic knowledge of AWS services like S3 and IAM.  
- ☁️ An AWS account with access and secret keys.  
- 🔑 OpenWeather API key (you can sign up [here](https://openweathermap.org/api)).  
- 🖥️ An integrated development environment like VS Code.  
- 💻 Bash scripting fundamentals.  
- 🐙 A GitHub account for version control.  

---

## 📂 Setting Up the Project

The first step was organizing the project directory structure. Here’s how I structured it:

```bash
mkdir weather-dashboard
cd weather-dashboard/
mkdir src tests data
touch src/__init__.py src/weather_dashboard.py
touch requirements.txt README.md .env
```

### 📝 Ignoring Unnecessary Files

Next, I created a `.gitignore` file to specify which files should not be tracked by Git. This helps keep the repository clean and secure.

```bash
echo ".env" >> .gitignore
echo ".zip" >> .gitignore
echo "__pycache__/" >> .gitignore
```

---

## 📦 Installing Dependencies

I created a `requirements.txt` file to manage the dependencies for the project and installed them using `pip`.

```bash
echo "boto3==1.26.137" >> requirements.txt
echo "python-dotenv==1.0.0" >> requirements.txt
echo "requests==2.28.2" >> requirements.txt
pip install -r requirements.txt
```

### Included Libraries:
- **python-dotenv**: For managing environment variables.  
- **boto3**: AWS SDK for Python, used to interact with AWS services.  
- **requests**: For making HTTP requests to fetch data from the OpenWeather API.  

---

## 🔧 Environment Setup

Configuring AWS credentials and the OpenWeather API was the next critical step. Here’s how I did it:  

1. **Set up AWS CLI credentials**:
   ```bash
   aws configure
   ```
   It will ask for:
   - Access Key ID
   - Secret Access Key
   - Default Region
   - Output format (JSON)

2. **Configure environment variables**:
   ```bash
   echo "OPENWEATHER_API_KEY=<Your-Weather-Key>" >> .env
   echo "AWS_BUCKET_NAME=<your-bucket-name>" >> .env
   ```
   Make sure your S3 bucket name follows AWS's naming rules and is globally unique.

---

## 🐍 Writing and Running the Python Script

The main logic of the project was implemented in the `weather_dashboard.py` file located in the `src` folder. This script:
- Fetches weather data for cities listed in `data/cities.json`.  
- Saves the data in the specified AWS S3 bucket in JSON format.

To run the script:
```bash
python3 src/weather_dashboard.py
```

Once executed, the script creates an S3 bucket (if it doesn’t already exist) and uploads the fetched weather data. Don’t forget to delete the bucket after the project! 🧹

---

## 📊 Outcome and Learnings

This project was both challenging and rewarding! 💡 Here’s what I learned:  
1. 🌍 How to integrate APIs like OpenWeather with Python.  
2. 🪣 Interacting with AWS S3 using the Boto3 library.  
3. 🛠️ Debugging and resolving real-world errors through research and collaboration.  

The architecture I designed is simple yet effective, and it was exciting to see the pieces come together seamlessly.  

---

## 🔗 Resources  

Here are some references I used during the project:  
- [OpenWeather API Documentation](https://openweathermap.org/api) 🌦️  
- [AWS S3 Documentation](https://docs.aws.amazon.com/s3/index.html) 🪣  
- [AWS CLI Configuration](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html) 📟  

---

## 📝 Final Thoughts  

Working on this project was a fantastic learning experience. I highly recommend trying it out if you want to explore API integration and AWS services. You can find the complete code on my [GitHub repository](https://github.com/Mygithubneha/30DaysDevOpsChallenge).  

Thanks for reading! 😊 Let me know your thoughts or share your experiences with similar projects in the comments below. Happy coding! 👩‍💻👨‍💻
