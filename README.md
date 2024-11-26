# COVID-health-monitoring-system-

<h2>1 INTRODUCTION</h2>
<h3>1.1.	Objective</h3>
<p>Our aim was to create an innovative device which would effectively decrease the spread of COVID-19 in local shops and stores. This would further help local businesses who have been gravely affected due to the pandemic. We noticed that people are largely relying on online shopping lately. The pandemic along with the lack of necessary rules and regulations in place has created a fear of shopping from their local shops. This has massively affected these businesses.
This fear has also affected the social lives of people. We are social beings and living in isolation for such a long period of time impacts us negatively. Therefore, by minimizing the risk of going out can help us have a part of our life back.</p>

<h2>2	Innovation</h2>
<p>Social distancing can play a huge role in reducing the risk of infection. However, ensuring social distancing in public places is challenging. This can be achieved by ensuring a shop only permits a certain number of people. Thus, there will be enough space for people to maintain a safe distance. Another way is to debar people who may have been infected. One of the many ways to do this is by measuring the body temperature and checking if it is within the normal range.
Regularly sanitizing hands can contribute to the safety of people. Encouraging people to sanitize their hands while entering and exiting a shop can ensure this. These were our 3 areas of focus and thus the Covishield Room has 3 modules catering to each of these methods aimed at bringing normal life back.</p>

![image](https://github.com/user-attachments/assets/9a6b9a30-9d22-4e4b-bc8d-530b47d04a90)

  <h2>3. Methodology</h2>

  <h2>3.1 Approach</h2>
    <p>
        To make our project a success, we had to overcome many roadblocks. Our approach from the beginning was to come up with innovative ideas 
        as the pandemic was something new and to solve it we had to think out of the box. We had to make sure no human was required to operate 
        the machine and minimize the contact from the people being checked. 
    </p>
    <p>
        For the temperature checker, we used an infrared thermometer which works without touch. It is also automatic, which removes the need of a 
        person. The sanitizer dispenser is also no-touch, using sensors to dispense sanitizer. Another problem was us being at different places, 
        which made it more difficult to work. We used IoT to help us all test and see the working of the people counter. The one thing in our 
        mind at all times was to overcome the spread, and that pushed us to come up with innovative ideas.
    </p>

  <h2>3.2 Modules</h2>
    <p>We divided the project into 3 modules, so we all could work efficiently:</p>
    <ul>
        <li><strong>Temperature Checker:</strong> Measures the temperature of the visitor.</li>
        <li><strong>Automatic Sanitizer Dispenser:</strong> Dispenses sanitizer when its sensor detects movement.</li>
        <li><strong>People Counter:</strong> Counts the number of people in the room and makes sure it does not exceed a particular count.</li>
    </ul>

  <h3>3.2.1 People Counter</h3>
    <p>
        The function of the people counter is to keep a tab on the number of people in a room at a point in time by counting the number of 
        people entering and exiting. This part of the project has two lasers placed one after another with an LDR at one end of each laser. 
        The LDR detects the light that falls on it. 
    </p>
    <p>
        When a person attempts to enter the room, the first laser gets blocked, and the LDR sends a signal to the microcontroller, and the 
        count of the room is incremented. When a person attempts to exit, the second laser is blocked before the first one, and thus the 
        second LDR sends a signal. The count is then decremented. The people counter uses IoT to send live data for people to access from 
        any place.
    </p>

  <h4>3.2.1.1 Components</h4>
    <ul>
        <li><strong>ESP32:</strong> A low-cost, low-power system-on-chip microcontroller with integrated Wi-Fi and dual-mode Bluetooth.</li>
        <li><strong>LDR:</strong> A light-dependent resistor whose resistance decreases when the intensity of light increases.</li>
        <li><strong>Laser (5V 650nm 5mW):</strong> A laser diode module with a wavelength of 650nm, suitable for various applications.</li>
        <li><strong>Resistors:</strong> Basic components providing resistance to electrical current.</li>
        <li><strong>Breadboard:</strong> A simple device for creating circuits without soldering.</li>
        <li><strong>Power Supply Unit:</strong> Provides the required power for the device.</li>
        <li><strong>ThingSpeak:</strong> An IoT analytics platform to aggregate, visualize, and analyze live data streams.</li>
    </ul>

  <h4>3.2.1.2 Flowchart</h4>

![image](https://github.com/user-attachments/assets/1fe90c3e-4c7b-4530-94d3-e0f38f846c34)

  <h4>3.2.1.3 Pseudocode</h4>
    <pre>
Include libraries like wifi and thingspeak
Establish a Wi-Fi client
Define channel number of thingspeak
Define the write API key for thingspeak
Define all variables for LED and LDRs
Define count, total count, and government count

Setup:
- Establish serial communication of 115200 bits/s
- Begin Wi-Fi connection with ssid & password using wifi.begin()
- Print connection status
- Begin ThingSpeak communication
- Define pins of LDR and LED

Loop:
- Read LDR values
- If (LDR1-laser) is passed first and then (LDR2-laser) is passed:
  - Increment count
- Else if (LDR2-laser) is passed first and then (LDR1-laser) is passed:
  - Decrement count
- If count >= govt_count:
  - Turn green LED on
- Else:
  - Turn red LED on
- Display count field on ThingSpeak
    </pre>

    <h4>3.2.1.4 Circuit Diagram</h4>
    
    ![image](https://github.com/user-attachments/assets/dd388de8-9dee-4b34-92a9-7081d59b2801)
    <p align = center><em>FIG. 3. Circuit Diagram of People Counter</em></p>

<h3>3.2.2 Contactless Infrared Thermometer</h3>
<p>
    The purpose of the contactless infrared thermometer is to measure the temperature of everyone who enters the room. It then shows a red or green light depending on the measured temperature. If the temperature is above a certain threshold, a green light will be visible, indicating that the person can enter. However, if the temperature is above the normal temperature, a red light will be displayed, debarring the person from entering. This reduces the chance of infection for other people in the room.
</p>

<h4>3.2.2.1 Components</h4>
<ul>
    <li><strong>Arduino Uno:</strong> An open-source microcontroller board based on the Microchip ATmega328P microcontroller and developed by Arduino.cc. The board is equipped with sets of digital and analog input/output pins that may be interfaced with various expansion boards and other circuits.</li>
    <li><strong>MLX90614:</strong> An infrared thermometer for non-contact temperature measurements.
        <ul>
            <li>Small size and low cost</li>
            <li>Easy to integrate</li>
            <li>Wide temperature range: -40 to 125°C for sensor temperature and -70 to 380°C for object temperature</li>
            <li>High accuracy of 0.5°C over a wide temperature range</li>
        </ul>
    </li>
    <li><strong>FC-51 IR Sensor:</strong> An electronic device that measures and detects infrared radiation in its surrounding environment.</li>
</ul>

<h4>3.2.2.2 Flowchart</h4>

![image](https://github.com/user-attachments/assets/a6a9e506-1a83-4721-ac75-797d520c4c11)
<p align = center><em>FIG. 4. Flowchart of Contactless Infrared Thermometer</em></p>

<h4>3.2.2.3 Pseudocode</h4>
<pre>
int IR_Sensor=2; 
int gled=3;
int rled=4;

Setup:
- Print "Adafruit MLX90614 test begin"
- Set IR_Sensor = INPUT
- Set Green LED = OUTPUT
- Set Red LED = OUTPUT

Loop:
- DigitalRead (IR_Sensor)
- If data = 1:
  - Read temperature in deg
  - Delay (500)
  - If temperature >= 37.8:
    - Red LED = ON
    - Green LED = OFF
  - Else:
    - Red LED = OFF
    - Green LED = ON
</pre>

<h4>3.2.2.4 Circuit Diagram</h4>

![image](https://github.com/user-attachments/assets/894bd8a1-8d17-4e97-95eb-207e6a5776fc)
<p align = center><em>FIG. 5. Circuit diagram of Contactless Infrared Thermometer</em></p>

<h3>3.2.3 Automatic Sanitizer Dispenser</h3>
<p>
    The automatic sanitizer dispenser dispenses sanitizer to everyone who enters the room, ensuring that the chances of COVID infection are minimized. The dispenser does not require any contact, which further ensures minimal risk. A sensor detects motion, and sanitizer is pumped with the help of a microcontroller and a DC pump.
</p>

<h4>3.2.3.1 Components</h4>
<ul>
    <li><strong>Arduino Uno:</strong> An open-source microcontroller board based on the Microchip ATmega328P microcontroller and developed by Arduino.cc.</li>
    <li><strong>Jumper Cables:</strong> Thick electric cables with clips at either end, commonly used for charging or connecting components.</li>
    <li><strong>NPN Transistor:</strong> Amplifies weak signals entering the base and produces strong signals at the collector end.</li>
    <li><strong>HC-SR04 Ultrasonic Sensor:</strong> Measures distance using ultrasonic waves.
        <ul>
            <li>Operating voltage: +5V</li>
            <li>Measuring Distance: 2cm to 450cm</li>
            <li>Accuracy: 3mm</li>
        </ul>
    </li>
    <li><strong>5V DC Pump:</strong> Uses direct current to pump fluids.</li>
    <li><strong>Breadboard:</strong> For designing circuits without soldering.</li>
    <li><strong>1N4007 Si Diode:</strong> A general-purpose silicon rectifier diode.</li>
    <li><strong>Pump Hose:</strong> Used to pump fluids, such as sanitizer.</li>
</ul>

<h4>3.2.3.2 Flowchart</h4>

![image](https://github.com/user-attachments/assets/d7033806-391b-4665-b57f-a51c196d1f2f)
<p align = center><em>FIG. 6. Flowchart of Automatic Sanitizer Dispenser</em></p>

<h4>3.2.3.3 Pseudocode</h4>
<pre>
Setup:
- Define ECHO_PIN, TRIG_PIN, MOTOR_PIN
- Define float variables for distance and duration
- Set ECHO_PIN as INPUT
- Set TRIG_PIN and MOTOR_PIN as OUTPUT

Loop:
- Write HIGH to TRIG_PIN, delay 10ms, then write LOW
- Calculate duration and distance
- If distance < THRESHOLD:
  - Write HIGH to MOTOR_PIN
- Else:
  - Write LOW to MOTOR_PIN
</pre>

<h4>3.2.3.4 Circuit Diagram</h4>

![image](https://github.com/user-attachments/assets/97f582dc-7762-4318-9b7f-f21b7e126814)
<p align = center><em>FIG. 7. Circuit diagram of Automatic Sanitizer Dispenser</em></p>

  <h2>4. Results</h2>
    <h3>Values received by ThingSpeak Platform</h3>
    
  ![image](https://github.com/user-attachments/assets/5ab93cc1-bca7-4407-8644-4570348c6af4)
    <p align = center><em>FIG. 8.1 ThingSpeak channel for People Counter</em></p>
    
  ![image](https://github.com/user-attachments/assets/7d1a484e-12d3-433a-a21a-680d81f5230a)
    <p align = center><em>FIG. 8.2 Live data of People Counter</em></p>

</body>
</html>
