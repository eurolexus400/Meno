# Meno v0
06/12/2017
Michael Esquivel
Automated Watering System

This system is designed to give optimal variability to the customer.  Currently the system is designed to run 6 valves for X amount of minutes.

#SimpleWaterTimerNanoV0
***********************
06/12/2017
*libraries: CountUpDownTimer, EEPROM, RTClib, Wire, SPI, SD
*
*User Defined: Relay0 - Relay5, WaterLength, num_pins
*User Defined Notes: Adjust the pin allocation table (lines 12 thru 17) to your corresponding pin designations.  Adjust the WaterLength (line 23) to the amount of watering time needed.  Adjust the number of pins (valves) you interact with.
*
*System Notes: Currently, the system is a timer-based system designed around the DS1307 real-time clock.  The time is compared, which initiates the water flag to True, triggering the valve 0 to start.  The controller waits for the timer to hit 0 thereby incrementing the valve, re-establishes the timer, saves data to the SD card, echos the data to the Serial Monitor, and loops until all 6 valves are complete.  When the valve have been cycled through the Water Flag gets set back to False stopping the valves have been cycled through and then the controller waits for the same (currently hour = 18) hour comparitor to start all over again.
***********************

***In the future***
Sensors: 
1: Homemade Soil Moisture sensors (Gypsum and Stainless Steel Bolts) measure the resistance values between electrodes in a alternating current.  The input gets switched in ms (swapping polarity to slow the electrolisis affect) and then averages the readings.  This value gets stored to the SD card.  Note: Each soil sensor will need to get characterized due to the inconstencies in (garage) manufacturing.  To make calculation easy, the values will be taken linearly from min to max and applied accordingly.  The plan is to arrange three sensors measurements at three depths (1 ft, 2 ft, and 3 ft).  We will gather data on the soak rate and soil moisture for each sensor in the sensor array.
2: Temperature (LM34) sensor
3: Light (Cds Light Dependent Resistor (LDR) 200K ohm) sensor
