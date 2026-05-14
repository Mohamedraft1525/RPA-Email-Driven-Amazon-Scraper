# RPA-Email-Driven-Amazon-Scraper
End-to-End RPA Automation Bot (Gmail → Amazon → Excel → Email)
Overview

This project is an end-to-end Robotic Process Automation (RPA) solution developed using UiPath.
The automation handles the complete lifecycle of receiving product requests through Gmail, validating the request, scraping Amazon product data, generating structured Excel reports, and sending the results back to the requester automatically without human intervention.

The project was developed as part of a technical assessment to demonstrate practical RPA development skills, including email automation, web scraping, Excel processing, credential management, and workflow orchestration.

Business Scenario

Many business operations still rely on manual repetitive tasks such as:

Reading incoming request emails
Extracting product information manually
Searching products online
Copying data into reports
Sending response emails

This process consumes time, increases operational cost, and introduces human error.

The automation bot eliminates these manual steps by creating a fully automated workflow capable of processing requests continuously and consistently.

Workflow Description
1. Gmail Monitoring

The workflow starts by monitoring a Gmail inbox using the Gmail Integration Service.

Trigger Logic

The automation is triggered whenever:

A new email arrives
The email subject contains the keyword "Amazon"

This event-driven approach avoids unnecessary polling and improves efficiency.

2. Attachment Validation

After receiving the email, the bot validates whether the required Excel attachment exists.

Validation Rules
If the attachment is missing:
The workflow sends an automatic error email to the sender
The process stops safely
If the attachment exists:
The workflow proceeds to data extraction

This validation layer improves reliability and prevents workflow failures caused by invalid requests.

3. Reading Product Data

The attachment contains a list of products requested by the sender.

The workflow:

Reads the Excel file
Extracts product names dynamically
Stores the data in structured variables and DataTables

The solution supports scalable processing for multiple products in a single request.

4. Amazon Web Automation

For each product in the Excel file, the bot performs automated browser interactions on Amazon.

Automation Steps
Opens Amazon website
Searches for the product
Navigates through the first search results page
Extracts:
Product Name
Product Price
Product Description
Automation Techniques Used
Modern UI Automation activities
Dynamic selectors
Element targeting
Retry mechanisms for unstable UI elements
5. Excel Report Generation

After scraping product information, the bot generates a structured Excel report.

Output Design
One worksheet per product
Organized product details
Timestamp-based file naming

Example:

Amazon_Report_2026_05_14_10_30.xlsx

Timestamping prevents overwriting previous reports and improves report traceability.

6. Email Response Automation

Once the report is generated, the workflow automatically sends the Excel file back to the original sender.

Email Features
Automatic reply handling
Attachment delivery
Secure authentication using Orchestrator Assets
SMTP-based email sending
Security Implementation

Security was considered during development to avoid exposing sensitive information.

Security Practices
No hardcoded credentials
Gmail credentials stored securely in UiPath Orchestrator Assets
Controlled email access
Safe attachment validation
Error Handling Strategy

The project includes multiple validation and recovery layers.

Current Handling
Missing attachment validation
UI element timeout handling
Safe workflow termination
Automated error email responses
Planned Improvements

The next phase of the project includes:

Refactoring using REFramework
Centralized exception handling
Transaction retry logic
Enhanced logging
Queue-based processing
Technologies Used
Technology	Purpose
UiPath Studio	Workflow Development
Gmail Integration Service	Email Triggering
Excel Activities	Reading/Writing Excel Files
Modern UI Automation	Amazon Web Scraping
UiPath Orchestrator	Credential Management
SMTP	Email Delivery
Project Architecture
Gmail Trigger
      ↓
Attachment Validation
      ↓
Read Excel Product List
      ↓
Amazon Web Scraping
      ↓
Generate Excel Report
      ↓
Send Email Response
Scalability Considerations

The project was designed with future production deployment in mind.

Future scalability enhancements include:

REFramework implementation
Orchestrator deployment
Queue processing
Centralized logging
Scheduling and monitoring
Enhanced retry mechanisms
Learning Outcomes

This project helped strengthen practical experience in:

End-to-end RPA development
Event-driven automation
Email automation workflows
Web scraping using UiPath
Excel automation
Secure credential management
Exception handling design
Workflow structuring and modularization
Author

Mohamed Raafat

Email: mohamedraafat2535@gmail.com

GitHub: github.com/Mohamedraft1525

LinkedIn: linkedin.com/in/mohamed-raafat-5b63702ab
