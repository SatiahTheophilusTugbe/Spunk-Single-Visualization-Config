# <h1> SPLUNK DASHBOARD AND VISUALIZATION SETUP </h1>
# Project Overview
This project provides a step-by-step guide for visualizing and monitoring web traffic data using Splunk. The data in question is focused on `POST` events, and through various visualization tools like **radial gauges**, **pie charts**, and **geographic maps**, you’ll gain insights into server request patterns and create dashboards to consolidate and monitor these metrics. Each visualization is saved as a report, which is then assembled into a Splunk dashboard for monitoring and alerting.

# Detail Steps
# Upload the radialgauge.csv file to your Splunk environment:
Navigate to splunk/logs/Week-2-Day-1-Logs and upload the radialgauge.csv file.

![2](https://github.com/user-attachments/assets/07170b15-afcc-46a9-83ae-a9bb154d5c4a)

Select all default options during the upload.

![3](https://github.com/user-attachments/assets/854f0e92-669a-4596-b703-c3f1302f6abc)

## Single-Value Visualization (Radial Gauge)
In this exercise, I created a radial gauge to monitor the number of "POST" requests per hour.
- Search: Use the following SPL query to count the number of POST events:
- Query: source="radialgauge.csv" http_method=POST | stats count as total

![4](https://github.com/user-attachments/assets/ba922081-fe5b-4eab-bf3d-7624fc3b26a6)

# Create the Visualization:
- Go to Visualization > Radial Gauge.
- Set the ranges under Format > Color Ranges > Manual. For example:
- Green: 0–400
- Yellow: 400–1000
- Red: 1000–2000
- Save the visualization as "Radial Gauge – POST request monitor".

![5](https://github.com/user-attachments/assets/8e4b12e5-1610-4488-bd15-f622521ee58c)

# Alert Setup:
Create an alert that triggers when the count reaches the red range (e.g., 1200+ POST requests/hour).

![6](https://github.com/user-attachments/assets/88d443ac-fe41-4171-b44f-f96f13492424)

# Quering Successful Account Logged on Events
Uploading the Source document:
- Locate Source File:Source="demo_winlogs.csv" host="WinsLogs" sourcetype="csv" and injest into Splunk

![7a](https://github.com/user-attachments/assets/7eb73834-c556-4ad8-9855-75ddddfac25e)

Open your Splunk search interface:
- From the left hand menu
- Drill down to subject
- From the pop-up to the left
- Select "An account was successfully logged on"

![8a](https://github.com/user-attachments/assets/600e3f93-f5bc-4fcf-a4b8-a3a2d7cf8bc4)

Use the following Splunk Query Language (SPL) to find events where the subject is "An account was successfully logged on":

- Query: host="WinsLogs" sourcetype="csv" subject="An account was successfully logged on"

![9a](https://github.com/user-attachments/assets/e49f2776-eec7-437f-b06d-fd2731f68d91)

# Create the Visualization:
- Graphing the query and also piping the top 20 successful log by user

![10a](https://github.com/user-attachments/assets/baac88c4-e82a-4f23-bbb2-b28692274e3a)

- Pie Chart Representation

![11a](https://github.com/user-attachments/assets/ccbfcda2-c7cc-439f-80ea-1c2ee565ca0f)

# Creating a report for the Pie Chart Logins

- ![12a](https://github.com/user-attachments/assets/d1119f23-6b03-4aa0-bb87-d926746a3927)





