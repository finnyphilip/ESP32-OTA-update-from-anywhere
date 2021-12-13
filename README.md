# ESP32 OTA update over Internet
Perform OTA update for ESP32 outside local network using NGROK port forwarding
## Header files
- #include <AsyncTCP.h>
- #include <ESPAsyncWebServer.h>
- #include <AsyncElegantOTA.h>

These header files create partitions inside ESP32 flash memory to receive new firmware and correspondingly 
changing bootloader
AsyncElegant web server provides a better interface for update operation.

## Steps to Follow
 1. Flash the firmware
 2. The IP address of ESP32 is displayed on serial monitor.
#### NGROK Tunnelling
1. Create an account in https://ngrok.com , A personal authoken can be obtained.
2. Download NGROK from https://dashboard.ngrok.com/get-started/setup
3. Run ngrok
4. Enter this command in the command line -- ngrok authtoken *authtoken*
5. Replace the IP address and enter this command -- ngrok tcp *IP_ADDRESS*:8888 --authtoken *authtoken*
6. The local IP is forwarded to the ngrok unique IP address. Copy the tunnel URL
7. TCP in the tunnel URL can be replaced with HTTP and enter the URL in any web browser, to access the web server
 #### Flashing new firmware
 In the Asyncwebserver, click on choose file and choose the binary file of new the firmware.
 
