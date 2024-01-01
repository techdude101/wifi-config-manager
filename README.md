# WiFi Config Manager Library

Library to allow a user to configure WiFi connection settings via WiFi softAP.

## Sample use case (ESP32, ESP8266): 
  ### Scenario 1 - firt power on (no WiFi config stored in flash or EEPROM)  
  #### Start the softAP & restart when configuration is set

1. Device powers up and a user connects to the softAP. 
2. User navigates to the web page, enters WiFi info and clicks 'Save'. 
3. Device reboots and connects to the WiFi network the user has specified in step 2. 

### Scenario 2 - batteries changed (WiFi config stored in flash or EEPROM)
  Start the softAP for a period of time to allow a user to connect and change config
  - If a device connects stop the timer
  - If the timer elapses,  connect to the WiFi network

### Scenario 3 - Device restarts to apply WiFi config
Connect to the WiFi network

### Scenario 4 - WiFi network is not in range (WiFi config stored in flash or EEPROM)
Same behaviour as in scenario 2.  
  Start the softAP for a period of time to allow a user to connect and change config
  - If a device connects stop the timer
  - If the timer elapses,  connect to the WiFi network

### Scenario 5 - WiFi network name or password has been changed on the router / AP (WiFi config stored in flash or EEPROM)
Same behaviour as in scenario 2.  
Start the softAP for a period of time to allow a user to connect and change config
- If a device connects, stop the timer
- If the timer elapses, connect to the WiFi network