# Cybersecurity 150 lab

# Name of the project:
wifi-killer

# Purpose:
Create an ESP32-S2 project using the ESP32CAM.
This project introduces an universal tool for ESP32 platform for implementing various Wi-Fi attacks.
includes Wi-Fi attacks itself like capturing PMKIDs from handshakes, or handshakes themselves by different methods like starting rogue duplicated AP or sending deauthentication frames directly, etc...

# Equipment
ESP32-S2
Data cable
Laptop
USB to USB C Adapter

# Documentation Followed
https://github.com/risinek/esp32-wifi-penetration-tool
https://www.youtube.com/watch?v=YjekZXoy91Y&t=0s
https://www.youtube.com/watch?v=dRoXJLPN3RE
https://docs.espressif.com/projects/esp-idf/en/v4.4.1/esp32/get-started/index.html
https://docs.espressif.com/projects/esptool/en/latest/esp32/advanced-topics/firmware-image-format.html?highlight=image
https://docs.espressif.com/projects/esptool/en/latest/esp32/
https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads

# Steps I followed
# step 1:
I first went to a this github repository "https://github.com/risinek/esp32-wifi-penetration-tool" 
# step 2:
I downloaded the repository as a zip and i unziped it at my downloads folder.
# step 3:
I downloaded all the drivers needed for the esp32 board and made  sure python was installed
# step 4:
Open my terminal and ran the command "brew install esptool"
# step 5:
in the terminal i navigated to the folder that  i unziped.
# step 6: 
run the command "esptool.py -p /dev/cu.usbmodem01 -b 115200 --after hard_reset write_flash --flash_mode dio --flash_freq 40m --flash_size detect 0x8000 build/partition_table/partition-table.bin 0x1000 build/bootloader/bootloader.bin 0x10000 build/esp32-wifi-penetration-tool.bin"
# step 7:
look around half the internet because it wouldnt upload and i would get one of many erros like this "WARNING: ESP32-S2 (revision v0.0) chip was placed into download mode using GPIO0.
esptool.py can not exit the download mode over USB. To run the app, reset the chip manually.
To suppress this note, set --after option to 'no_reset'."
# step 8: 
use a different board and run the same command with a different port "esptool.py -p /dev/cu.usbserial-1410 -b 115200 --after hard_reset write_flash --flash_mode dio --flash_freq 40m --flash_size detect 0x8000 build/partition_table/partition-table.bin 0x1000 build/bootloader/bootloader.bin 0x10000 build/esp32-wifi-penetration-tool.bin --flash_size=keep"
# step 9:
after  the command runs succesfully In browser open 192.168.4.1 and you should see a web client to configure and control tool

# PROBLEMS
I was encountering many problems when trying to upload the script to the board and i first i didnt know why. 
I started to look around the interner and i tried to installing different drivers and i also installed different modules. 
I kept getting different errors the more i messed around until i came over a error message where it was telling me i was upoloading it to the wrong board.
After i tried a different board provided by the proffesor i was able to upload it succesfully and access the tool on the web browser.


