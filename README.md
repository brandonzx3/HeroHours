# HeroHours
Team 5892's attendance solution
### A lone redacted screenshot (submit a pr if you have a better one)
![image](https://user-images.githubusercontent.com/20732350/149432819-06f04b8b-c6f8-4219-9990-91f981b9d769.png)

## How to install
### Setting up google sheets and apps script
1. Create a new Google Sheet and open Google AppsScript
![image](https://user-images.githubusercontent.com/20732350/149431170-363128c1-8ad5-47df-a23c-cbe514449611.png)
2. Delete the contents of Code.gs and paste in the contents of Code.gs from this repository
![image](https://user-images.githubusercontent.com/20732350/149431384-39dec44a-4588-4b13-bab7-dd52f28bf042.png)
3. Click the Deploy button, then click New Deployment
![image](https://user-images.githubusercontent.com/20732350/149431536-3b7843b1-1447-4107-b1bd-8cd2cf46a658.png)
4. Make sure the Deployment Type is Web App, Execute As is set to me (youremail), and Who Has Access is set to Anyone.
![image](https://user-images.githubusercontent.com/20732350/149431648-7195abdd-9479-4bdf-b372-7de9cea70cd4.png)
![image](https://user-images.githubusercontent.com/20732350/149431737-ce1ee7d6-9b2e-4e98-999e-5821f1120c12.png)
5. Note the WebApp URL for later
![image](https://user-images.githubusercontent.com/20732350/149431904-28357011-3868-4a14-92f2-4bd67b910ed9.png)
6. Upload HeroHours Template as a template and replace all existing sheet content
### Setting up your kiosk
1. Install a webserver of some sort onto your kiosk (I use python3's http.server)
2. Copy HeroHours into a directory of your choice
3. Make a copy of config.json.sample and rename it to config.json
4. Add your WebApp URL to your config.json in the endpoint field 
5. Point your webserve to that directory (With python3 http.server: python3 -m http.server --directory /path/to/HeroHoursFiles)
6. Point your browser of choice at localhost:port (With python3 http.server: localhost:8000)
7. Setup a script to run your webserver and browser of choice on boot (On raspberry pi, add commands to run at /home/pi/.config/lxsession/LXDE-pi/autostart)
#### Is a webserver neccesary?
Unfortunately it is. I decided to extract environment variables to a json file so that I could easily gitignore them. The only way for javascript to get to the json file is for the json file to be hosted on a webserver. If anyone has an alternative way please let me know. I too would rather not have to run a webserver.
