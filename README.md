# Aws-2tier-project
A project using Aws S3 and lambda to aggregate the employee salary details

Project Overview

This project demonstrates a 2-Tier AWS architecture where data uploaded to Amazon S3 is automatically processed using AWS Lambda. The system performs serverless data processing without managing any servers and generates aggregated results based on business logic.

The main objective of this project is to showcase event-driven architecture, serverless computing, and AWS cloud services integration.

🏗️ Architecture Overview (2-Tier)

Tier 1 – Storage Layer

Amazon S3 bucket stores CSV files containing employee data.

Tier 2 – Processing Layer

AWS Lambda function is triggered automatically when a file is uploaded to the S3 bucket.

The Lambda function reads and processes the data and writes the aggregated output back to S3.

🔧 AWS Services Used

Amazon S3 – Object storage for CSV input and output files

AWS Lambda – Serverless compute service to process uploaded data

AWS IAM – Role and permissions for Lambda to access S3

Boto3 – AWS SDK for Python used inside Lambda

📂 Input Data

CSV file (e.g., employee3.csv) containing employee details such as:

Employee ID

Employee Name

Salary

Country (India / USA)

⚙️ Project Workflow

User uploads a CSV file to an S3 bucket.

S3 generates an event notification.

AWS Lambda function is triggered automatically.

Lambda reads the CSV file from S3.

The function:

Separates employee salaries by country (India and USA)

Calculates total salary expenditure for each country

Aggregated results are written back to the same S3 bucket as an output object.

Execution logs are stored in Amazon CloudWatch Logs.

🧠 Lambda Function Logic

Reads CSV file from S3 using boto3

Parses the file using Python csv module

Filters salary data based on country

Calculates total salary spend for India and USA

Uploads the result back to S3 as an aggregated output

📤 Output

Aggregated salary data stored in S3:

total india,us salary spend is ,(India_Total, USA_Total)
