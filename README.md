# Steadymate Monitor
Steadymate is a body temperature monitor specifically designed for children who suffer from CIPA. This project was designed during a 24-hour biomedical hackathon, and features the joint effort of Katarina Chiam, Mirjana Mijalkovic, Julia Wang and Kelvin Cui.
<img src = "https://raw.githubusercontent.com/ntnox/steadymate/master/Steadmate_Device.jpg">

## Background Info
Congenitive Inensitivity to Pain and Anhydrosis, or CIPA, is a rare condition that prevents childen from feeling pain or heat. As a result, many childen who suffer from CIPA often injure themselves without realizing it. As they are unable to feel heat, and being kids, they are at a high risk of heat related injuries, such as heat strokes. We wanted to focus on this aspect, and find a way to alert both the child and parent as body temperatures reach critical levels.

## How it works
There are two aspects to our solution - hardware monitoring and software reporting. 

### Hardware
For the hardware aspect, we created a bluetooth enabled wristband using Arduino. This wristband featured a temperature monitor, as well as visual, tactile, and auditory feedback for the child. As their body temperature exceeds 38 degrees, an auditory buzzer, vibration feedback, and a flashing light alerts the child to the situation. These feedback devices increase in severity as the temperature increases, up to 40 degrees. The wristband also features a sensor that alerts parents when the wristband is taken off or lost.

### Software
As for the software, we were constrained by our 24-hour time limit. As a result, we decided to create a companion android app in MIT App Inventor to save on time. The companion app features live temperature reports, and is designed to be used by either older children, or by the guardians of younger kids. It not only reports temperature at all times, but also pushes notifications if the temperature exceeds certain dangerous thresholds. 

## Lessons Learned
If we were to do this project again, we would reconsider connectivity - bluetooth has a certain range, and if the child is out of the range, the bracelet loses connectivity with the companion app. A possible solution to this would be to allow the device to connect over Wifi as an IOT device, either with standalone celluar, or using the child's phone as a bridge.

## File guide
steadymate.ino:
This is the arduino file for the hardware portion.

steadymate_android.aia:
This is the project file for the accompanying Android App. Due to the time constraints of this project, our team felt that we wanted to get the app as quickly as possible, and MIT App Inventor V2 was the best tool considering our circumstances. Feel free to open the .aia in App Inventor V2 to have a peek at how it works.

schematic.png
This is the schematic of how to wire the Arduino board.
It features the following components : 
  - Thermistor for skin temperature detection
  - LED for visual feedback of current skin temp (Green = okay, Red = Temp critically high, etc)
  - Speaker for auditory feedback of current skin temp (No sound = okay, Rapid beeping = Temp critically high)
  - A vibration motor for tactile feedback of current skin temp (No buzzing = okay, Rapid buzzing = Temp critically high)
  - A physical button to alert the guardian if the bracelet is taken off
  - A bluetooth chip to send live data to the android app.

the two Steadmate_xx.png are photos of the device!
