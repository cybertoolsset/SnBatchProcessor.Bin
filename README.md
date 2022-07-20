# SnBatchProcessor

Demo of 0.4.0 

https://youtu.be/Y8r33wX0F5M

Demo how it run in Docker

https://youtu.be/-huNqyeqFBU

Demo of basic functionality

https://youtu.be/AdAT1q4QQQo

## Install

### Prerequsites:

1. Setup Chrome version 103 or fresh Firefox. To use Firefox you will have to change browser type in appconfig.json. Default is Chrome.
2. Prepare social networks accounts. Youtube, Facebook, Twitter, Instagram, TikTok, Telegram, Email. You may use newly created accounts. For Telegram it's reccomended to use separate account on dedicated pnone number (how to get separate phone number pls read below).
3. Ensure that chrome is in your PATH

### Installation sequence 

1. Download archve correspondint to your OS
2. Unpack the archive to sume folder.
3. For Linux mark **chromedriver** and **SnBatchProcessor.Server** as executebles. For OsX probaly too.
4. Run **SnBatchProcessor.Server** from a terminal console
5. Launch your browser and go to http://localhost:5458
6. Navigate to Setup page and launch browser
7. Log in into your social networks accounts.
8. Exit from the browser
9. Enter phone number and ask to Send Code for Telegram account
10. Check your Telegram client for the code
11. Enture the code and Sing In.
12. Copy-paste some text included URLs to socila network account on Report Raw page. Push the text. 
13. Switch  to Events page and ensure that all works. 
14. To setup SMTP and FROM options for Email reporting you have to manually edit appconfig.json
15. Enjoy

The application supports multiple profiles, but has only basic UI support for this.


## How to get additinal phone number for Telegram
1. It's strongly recommeneded to create separate Telegram account with new phone number. You may use:
 
   1.1 A service from mobile operator to bind second number to your SIM card.

   1.2 By a virtual phone number in Skype.

   1.3 By a virtual phone number in Google Voice.

   1.4 Use Next+ (Nextplus) application (service) on the same Android emulator
   
   1.5 By a phisical prepaid SIM card and use it as second or in separate phone.

   1.6 By a virtual phone number with any other appropriate service. All you need is ability to receive SMS.

| Service | One time number | Permanent number |
| :----- | :---: |  :---: |
| Zadarma | — | paid |
| Twilio | — | paid |
| ZEBRAtelecom | — | paid |
| TextNow | free | paid |
| Comtube | paid | paid |
| Sms-reg.com | — | paid |
| Primatel | — | paid |
| Telphin | — | paid |
| Uiscom | — | paid |

2. Run Android emulator (as an example BlueStacks) and install Telegram Android client.
3. Launch the client and register new Telegram account with your newly created phone number. Use SMS code for registeration.
4. Wait 24h to get the newly created Telegram account availble to second login on another device.


## Setup email reporting

1. Create an email account. As an example, on GMail. 
2. Fill account email and corresponding SMTP server settings into a profile.
3. Each profile in appconfig.json designed to complain multiple target types (as an example, Telagram abuse email address) ent each teget type may have multiple "To" addresses.
4. Email profile in appconfig.json can have many complain message templates. The program will randomly select one of them. Email body template is an external file in "data" folder.
5. You may use local fake SMTP server (the link in Links section) to tesm email reporter.

## Run in Docker

1. Run container
```
docker run --name snbatch -p 6080:80 -p 5900:5900 -p 5458:5458 cybertoolsset/snbatchprocessor
```
2. Connect to the application with http://localhost:5458
2. Connect to the desktop in the container via noVNC web inteface http://locahost:6080. Or you may yse any VNC client to localhost:5900.
2. Follow installation sequence from step [6]. Be noted that Docker version of the application uses Firefox browser, not Chrome as usual version. Also for edit appsettings.json you may install **nano** editor into the container.
