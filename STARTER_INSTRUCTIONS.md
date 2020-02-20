# WHATSAPP CODE BLASTER - VEDANT GHODKE

## Python Automation using Selenium &amp; Scheduling of messages and media

## Objective:
This code is used to automate Whatsapp through Whatsapp web. We can
add number of contacts whom we want to send messages or media
attachments ( like videos, images or documents). Selenium, Autoit and Schedule have
been used one for automation and other for scheduling messages.

---

## Purpose of development:
This contains a basic idea of my way to integrate a WhatsApp with core ERP (Enterprise Resource Planning) softwares for data abstraction and mass blasting for enabling clients and customers for real time tracking and updates

---

## Installation

>$ pip install -r requirements.txt

OR

>$ pip install selenium
>
>$ pip install schedule
>
>$ pip install PyAutoIt

###### NOTE: If there is any issue in installation of pyautoit then clone the repo and install from repo. [LINK](https://github.com/jacexh/pyautoit)
---

### Platform: Windows
ChromeDriver used: If this versions becomes outdated or gives problem
download the latest version from <a href =
"http://chromedriver.chromium.org/downloads"> Download Link </a>

### Platform Mac
Remove the ChromeDriverused in the repository and install <a href =
"https://chromedriver.storage.googleapis.com/2.42/chromedriver_mac64.zip">Mac ChromeDrive Download Link</a>

>Set ChromeDriver path in function whatsapp_login()
><a href ="https://stackoverflow.com/a/44870398/6897603">Set
>  ChromeDriver Path in MacOS</a>

---
### For sending attachments you need to install AutoIt (optional, only if you want to send messages) | (Only FOR WINDOWS USERS):

You may install from the links given below or install from the folder
named "Install AutoIt for Sending Attachments" in the repository.

<a href = "https://www.autoitscript.com/site/autoit/downloads/">Official
Website Download Webpage</a>

<a href =
"https://www.autoitscript.com/cgi-bin/getfile.pl?autoit3/autoit-v3-setup.exe"> Installation Link of AutoIt.exe</a>

<a href =
"https://www.autoitscript.com/cgi-bin/getfile.pl?../autoit3/scite/download/SciTE4AutoIt3.exe"> AutoitScript Editor (optional to install) </a>

Installation is pretty simple. No changes in setting are required. Few clicks on Next button and you are done!

---

## Feature Enhancement: 
QR CODE Scanning: I have added a cookie system that will save your session so that WhatsApp doesn't think you are logging in for the first time. By saving session data, you will have to scan QR Code to Login only once or till the time whatsapp does not log you out from whatsappweb.com

NOTE: A folder User_Data will be created which has all your session information. Keep this Folder VERY SAFE! 

## Code:
### input_contacts()

In this function, contacts list can be hardcoded or you can give input
accordingly.(Make changes in 'Mob_Nos_2.xlsx' excel sheet according to you)


```
1.Enter Saved Contact number->
2.Enter Unsaved Contact number->
Enter your choice(1 or 2):->1
# For saved Contacts
Enter number of Contacts to add(count)->1
Enter contact name(text)->Shaurya
# For unsaved Contacts
Enter number of unsaved Contacts to add(count)->1
Enter unsaved contact number with country code(interger)->919899123456
```

### NOTE: For unsaved contacts:
Do enter your country code then contact number.
>Use: 9197798671025
>
>Don't Use: +917798671025



### input_message()
In this function we take input of message to send to all the contacts from user (saved or unsaved).

Example:
>Enter the msg to send-> Good morning

### Enter choice to schedule message or not.
>Do you want to schedule your Message(yes/no): yes
>
>input time in 24 hour (HH:MM) format - 10:10

NOTE: If testing program for the first time scheduling should be `no`, to check if it is working perfectly.

### Enter choice whether to send attachments or not.
>Would you like to send attachment(yes/no): yes
>
>Answer the input with either a yes or no.

### send_attachments()
NOTE: Add photos or videos in the Media folder.

image_path = os.getcwd() +"\\Media\\" + 'goodmorning.jpg'

Example path to send goodmorning image to your listed contacts.

*   "hour" variable is used to check current Hour on the clock and
according image is sent to the Contact.
*   If the time is post 5:00 AM, and prior to 11:00 AM, schedule goodmorning image.
*   If the time is post 9:00 PM, schedule goodnight image.
*   If it's any other time, send howareyou image.

You can set your own photos at a particular time. Feel free to do that!

### send_files()
NOTE: Add the document in the documents folder.
>Would you file to send a Document file(yes/no): yes
>
>Enter the Document file name you want to send: opportunity

*   If the document file names are same then write the document name
with extension like opportunity.pdf or opportunity.txt


### Schedule messages and attachments
schedule.every().Monday.at("06:00").do(sender)

schedule.every().Tuesday.at("07:00").do(sender)

schedule.every().Friday.at("07:30").do(sender)

schedule.every().day.at("08:30").do(sender)

*   You make change these schedule days and time according to you.

---

## Author:
## <a href="https://www.linkedin.com/in/vedant-ghodke-34b124168/">VEDANT GHODKE</a>

vedantghodke@gmail.com

Cell: +91 7798671025

Feel free to mail me or call me up for any further queries! Always up for a brain-storming session and a great discussion!
