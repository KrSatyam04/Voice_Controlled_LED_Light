# Voice_Controlled_LED_Light
In this project, we make a voice controlled LED Light using Arduino Nano 33 IoT Board

    KUMAR SATYAM
    For ELECTRONICS FOR APPLIED PHYSICS
    DEPARTMENT OF PHYSICS AND ASTRONOMY
    UNIVERSITY OF BOLOGNA, ITALY

Equipments Used:

1. Arduino NANO 33 IoT
2. Breadboard
3. Jumper Cables
4. LED Light
5. USB 3.0 Data Cable

Software/Services used:

1. Arduino Create Agent
2. Blynk
3. IFTTT
4. Google Assistant

STEPS:
1. Configuring Arduino Nano 33 IoT
2. Downloading required librabries
3. Writing Program for Arduino and Uploading the program (Sketch)
4. Configuring Blynk and LED combination
5. Setting up IFTTT
6. "Ok Google! Light it up!"


## 1. Configuring Arduino Nano 33 IoT

The Arduino Nano 33 IoT is Arduino's smallest board to get started with Internet of Things (IoT). Using the popular Arm® Cortex®-M0 32-bit SAMD21 processor, it also features the powerful u-blox NINA-W102 Wi-Fi module and the ECC608A crypto-chip for security.

For more Details: https://docs.arduino.cc/hardware/nano-33-iot

  1.1. Install Arduino Create Agent
        https://create.arduino.cc/getting-started/plugin/download
        
  1.2. Connect Arduino Nano to Arduino Create Agent using data transfer capable USB 3.0 cable
  
  1.3. Plug in your Arduino Nano into Breadboard. (Remember, you may have to use more pressure than you would expect to plug the Arduino Nano in the breadboard. Go for it.)
  
  
## 2. Downloading required libraries
      The following libraries are required for this project:
      <SPI.h>
      <WiFiNINA.h>
      <BlynkSimpleWiFiNINA.h>
      
      It can be installed in Arduino Create from
        Sketch -> Include Libraries -> Manage Libraries
 
## 3. Writing the program for Arduino and Uploading the program (Sketch)
      
      For arduino, the program is called "Sketch" and the file extension is .ino
      
      Go to File -> New
      
      Copy and paste the code. (File named Blynk_Sketch.ino)
      Remember to edit the Blynk_Auth_Token, ssid and pass with your own.
      
      Upload the sketch.
      
## 4. Configuring Blynk and LED Combination

      Open Blynk App
      Create New Project
      Select hardware - Arduino Nano
      Connection Type - Wifi
      
      You will be sent a auth token on email. This auth_token has to be used in the sketch.
      Add Button
      Click Button to setup
      Select PIN (Arduino Nano 33 IoT Pin Diagram is avaiable in files as Arduino Nano Pin Diagram.png)
      Connect the LED to the PIN Selected.
      Remember, one pin will always go in GND(ground) and other pin will be connected to the other assigned numbers.
      
## 5. Setting Up IFTTT
      With the help of IFTTT, we will make our Google Assistant to communicate with Blynk Server and consequently to our Arduino Nano.
      In IFTTT, Click Create.
      
      Add "If This" as Google Assistant. 
        (You will have to connect connect the IFTTT to your Google Account.)
        (The language in Google Assistant should be configures as English to be able to use custom commands.)
        
        Select Trigger "Say a simple phrase"
        Input the voice command "Turn on RED Light". (Command can be cusomised)
        Another optional commands can be "Make it Red" or "Light it up".
        Input "What do you want to say in response" as "Command accepted",
        or "light turned on" or whatever you please.
        This will be the reply from Google Assistant if she understands and accepts the command.
        Select Language as "English". (other language can also be tried though)
        
      Add "Then That" as Make a web request
        In URL, enter: http://139.59.206.133/your_blynk_token/update/D3
        (D3 is pin name on Arduino Nano to which our LED is connected. Change accordingly)
        Select Method as PATCH
        Select Content Type as application/json
        Leave Additional Headers as blank
        Input in Body: ["1"]  (1 means swith on, as configured in Blynk)
        Save it.
        
      Repeat the steps for turning the light off.
      Change the command as "Turn Off ..." and change the Body as ["0"]
        
       
## 6. "Ok Google! Light it up!"

      Now, it's time to see the magic!
      
      Make sure your LED is connected to the right Arduino Nano Pins.
      Make sure your Arudion Nano is powered on.
      And make sure the wifi/hotspot is on for which it was configured earlier.
      
      If everthing is good, ask the google assistant: "Turn on the Red Light"
      Command Accepted!
      Congratulations! You did it!
      
      
