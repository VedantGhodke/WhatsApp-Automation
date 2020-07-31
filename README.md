# WhatsApp Automation Using Python
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://github.com/shauryauppal/PyWhatsapp)  [![License](https://img.shields.io/github/license/shauryauppal/PyWhatsapp.svg)](https://github.com/shauryauppal/PyWhatsapp/blob/master/LICENSE) [![GitHub stars](https://img.shields.io/github/stars/shauryauppal/PyWhatsapp.svg)](https://github.com/shauryauppal/PyWhatsapp/stargazers)  [![HitCount](http://hits.dwyl.io/shauryauppal/PyWhatsapp.svg)](http://hits.dwyl.io/shauryauppal/PyWhatsapp)

## Python Automation using Selenium And Scheduling of Messages and Media

## Objective:
This project is used to automate Whatsapp through Whatsapp Web. We can
add number of contacts to whom we want to send messages or share media
attachments (videos or images). Selenium, Autoit and Schedule have
been used; one for automation and other for scheduling messages.

---

## Use Case:
We can schedule Good Morning or Good Night messages with a nice picture
at a particular time to our loved ones. We can set reminders. Suppose at
12 o'clock you want to wish your friend happy birthday so schedule your
messages and sleep peacefully.

---

## Installation

>$ pip install -r requirements.txt

OR

>$ pip install selenium
>
>$ pip install schedule
>
>$ pip install PyAutoIt

###### NOTE: If there is any issue in installation of pyautoit then clone the repo and install from the following repository.

[LINK](https://github.com/jacexh/pyautoit)
---

### Platform: Windows
ChromeDriver used: If this versions becomes outdated or gives problem
download the latest version from <a href ="http://chromedriver.chromium.org/downloads">Windows ChromeDriver Download Link </a>

### Platform: Mac
Remove the ChromeDriver used in the repository and install <a href =
"https://chromedriver.storage.googleapis.com/2.42/chromedriver_mac64.zip">Mac ChromeDriver Download Link </a>

>Set ChromeDriver path in function whatsapp_login()><a href ="https://stackoverflow.com/a/44870398/6897603">Set>  ChromeDriver Path in MacOS</a>

---
### For sending attachments you need to install AutoIt (optional if you only want to send messages) | (Only for Windows users):

You may install from the links given below or install from the folder named "Install AutoIt for Sending Attachments" in this repository.

<a href = "https://www.autoitscript.com/site/autoit/downloads/">Official Website Download Webpage</a>

<a href = "https://www.autoitscript.com/cgi-bin/getfile.pl?autoit3/autoit-v3-setup.exe"> Installation Link of AutoIt.exe</a>

<a href = "https://www.autoitscript.com/cgi-bin/getfile.pl?../autoit3/scite/download/SciTE4AutoIt3.exe"> AutoitScript Editor (optional to install) </a>

Installation is pretty simple and no changes are required in settings, keep everything default. Few clicks on 'Next' and you are done.

---

## Feature Enhancement: 
QR CODE Scanning: On receiving a lot of complaints about QR Code scanning issue again and again, I have added a cookie system that will save your session so that WhatsApp doesn't think you are logging for first time. By saving session data you will have to scan QR Code to login only once or till the time WhatsApp does not log you out from whatsappweb.com

NOTE: A folder User_Data will be created which has all your session information. Keep this folder **VERY SAFE**. 

## Code:
### Added ArgParser
`python3 PyWhatsapp.py --help`<br>
  --chrome_driver_path (required) CHROME_DRIVER_PATH chromedriver executable path (MAC and Windows path would be different) <br>
  --message (optional) MESSAGE Enter the msg you want to send <br>
  --remove_cache (optional) REMOVE_CACHE Remove Cache | Scan QR again or Not <br>

For Windows: `python3 PyWhatsapp.py --chrome_driver_path './chromedriver.exe' --message 'Hi Vedant, How Are you?'`
<br>For MACOS: `python3 PyWhatsapp.py --chrome_driver_path './chromedriver' --message 'Hi Vedant, How Are you?'`

### input_contacts()

In this functions Contacts list can be hardcoded or you can give input
accordingly.(Make changes in Contact array according to you)


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
>Use: 919899123456
>
>Don't Use: +919899123456



### input_message()
In this function we take input of message to send to all the Contacts
list from user.

Example:
>Enter the msg to send-> Good morning

### Enter choice to schedule message or not.
>Do you want to schedule your Message(yes/no): yes
>
>input time in 24 hour (HH:MM) format - 10:10

NOTE: If testing program for the first time Scheduling should be `no`
inorder to check it is working perfectly.

### Enter choice whether to send attachments or not.
>Would you like to send attachment(yes/no): yes
>
>Answer the input with yes or no.

### send_attachments()
NOTE: Add Photos & Videos in the Media Folder.

image_path = os.getcwd() +"\\Media\\" + 'goodmorning.jpg'

Example path to send goodmorning image to your listed Contacts.

*   "hour" variable is used to check current Hour on the clock and
according image is sent to the Contact.
*   If time is after 5am and before 11am schedule goodmorning.jpg image.
*   If time is after 9pm schedule goodnight image.
*   If time is anyother send howareyou image.

You can set your own photos at a particular time feel free to do that.

### send_files()
NOTE: Add the document in the documents folder.
>Would you file to send a Document file(yes/no): yes
>
>Enter the Document file name you want to send: opportunity

*   If the document file names are same then write the document name
with extension like opportunity.pdf or opportunity.txt


### Schedule messages and Attachments
schedule.every().Monday.at("06:00").do(sender)

schedule.every().Tuesday.at("07:00").do(sender)

schedule.every().Friday.at("07:30").do(sender)

schedule.every().day.at("08:30").do(sender)

*   You make change these schedule days and time according to you.

---

### Input Screenshot:
<img
src="https://raw.githubusercontent.com/shauryauppal/PyWhatsapp/master/Input_Type.PNG" height=300/>

---

### Demo of Working (GIF)
<img
src="https://raw.githubusercontent.com/shauryauppal/PyWhatsapp/master/Media/Demo.gif" height=400 width=400/>

---

## License
License
Code and documentation are available according to the Apache License
(see <a href="https://github.com/VEDANTGHODKE/WhatsApp-Automation/LICENSE">LICENSE</a>).

---
