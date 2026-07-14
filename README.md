# Browser Cleanup Automation Script

## Overview

Browser Cleanup Automation is a Python-based utility designed to automatically remove browser history and cache files from Google Chrome and Microsoft Edge. 

The script is suitable for daily maintenance tasks on Windows computers and can be scheduled using Windows Task Scheduler. After cleanup, it generates a report containing the cleanup status and sends it via email to configured recipients using BCC.

---

## Features

- ✅ Automatically closes Google Chrome and Microsoft Edge
- ✅ Deletes Chrome browsing history
- ✅ Deletes Microsoft Edge browsing history
- ✅ Clears browser cache files
- ✅ Removes temporary browser cache folders
- ✅ Generates cleanup activity reports
- ✅ Sends email notification after completion
- ✅ Supports multiple email recipients using BCC
- ✅ Runs automatically through Windows Task Scheduler

---

## Technologies Used

| Technology | Purpose |
|------------|---------|
| Python 3 | Main scripting language |
| SMTP | Email notification service |
| Windows Task Scheduler | Automation |
| OS Module | System process management |
| shutil | Folder cleanup |
| Socket | Computer identification |

---

## Project Structure


Browser-Cleanup-Automation/
│
├── browser_cleanup.py # Main cleanup script
│
├── README.md # Project documentation
│
└── logs/ # (Optional) Cleanup logs


---

## Requirements

### Software Requirements

- Windows 10 / Windows 11
- Python 3.x installed
- Internet connection for email notification
- Gmail account with App Password enabled

---

## Python Libraries

This project uses built-in Python libraries:


os
shutil
socket
getpass
time
datetime
smtplib
email


No external packages are required.

---

# Installation

## 1. Install Python

Download Python from:

https://www.python.org/downloads/

Verify installation:

```bash
python --version
2. Clone or Copy Project

Example:

C:\Scripts\BrowserCleanup

Copy:

browser_cleanup.py

into the folder.

Configuration
Email Setup

Open:

browser_cleanup.py

Update:

gmail_user = "your_email@gmail.com"

gmail_bcc = [
    "recipient1@gmail.com",
    "recipient2@gmail.com"
]

gmail_app_password = "YOUR_APP_PASSWORD"
Gmail App Password

For Gmail SMTP authentication:

Enable 2-Step Verification
Create an App Password
Replace:
YOUR_APP_PASSWORD

with the generated password.

Browser Profiles

The script currently supports:

Google Chrome
C:\Users\<username>\AppData\Local\Google\Chrome\User Data\Profile 6
Microsoft Edge
C:\Users\<username>\AppData\Local\Microsoft\Edge\User Data\Default

If the user profile is different, update:

chrome_profile
edge_profile

inside the script.

Running Manually

Open Command Prompt:

cd C:\Scripts\BrowserCleanup

python browser_cleanup.py

Expected output:

Email sent successfully!
Automating with Windows Task Scheduler
Create Scheduled Task
Open:
Task Scheduler
Select:
Create Task
General Tab:

Enable:

Run whether user is logged on or not
Run with highest privileges
Trigger

Example:

Daily
Time: 06:00 AM
Action

Program:

python.exe

Arguments:

C:\Scripts\BrowserCleanup\browser_cleanup.py
Email Report Example
Browser Cleanup Report

Date:
2026-07-14 06:00:00

Computer:
DESKTOP-XXXX

User:
username


Cleanup Status:

Deleted file:
Chrome History

Deleted folder:
Chrome Cache


Completed Successfully
Security Recommendations
Do not store passwords directly in code

Avoid:

gmail_app_password = "password"

Recommended:

Use Windows Environment Variables:

GMAIL_APP_PASSWORD

and load it:

os.environ.get("GMAIL_APP_PASSWORD")
Important Notes

⚠️ The script deletes browser data permanently.

Before deployment:

Test with a non-production account
Confirm required browser profile paths
Avoid deleting cookies unless required

Deleting cookies will sign users out from websites.

Troubleshooting
Error: Access Denied

Example:

[WinError 5] Access is denied

Solution:

Run script as Administrator
Ensure Chrome/Edge are closed
Enable "Run with highest privileges" in Task Scheduler
Email Sending Failed

Check:

Gmail App Password
SMTP access
Internet connection
Firewall restrictions
Author

Richard Kiwale
IT Support
