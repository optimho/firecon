<h1>Firecon</h1>
<style>
p {indent-text: 0em;}
</style>

Allows one to enable and disable pre configured firewall rules on an edge router with a simple command line tool.
The tool can be installed on any computer on the same network as the router. 
netmiko can be configured to work on most routers, I only have the edge router so that's all I have to try it on.
To do this visit the netmiko api page and see if your device is listed and chage the device type in the config.ini file

The program has been written on a linux mint machine and has only been tested on linux.
It is possible running the scrip from a button push on a raspberry PI as a possibility. 

Obviously this is quite a custom piece of software for my application but is reasonably easy to expand on. 
The rules are set up in the edge router and tested then they can be disabled or enabled from this software.

It also nicely demonstrates how you can use the netmiko to control the edge router.
The application is intended as a command line tool so has a raft of options, although the 'enable' and 'disable' coare the 
The script called firecon can be called on very easily to switch the firewall rules on or off with command line switches.

The script can be run from a cron tool to make configuring of more complicated time of use and makes it easier to 
make a one time change (The I said get off the device now).

run the script with python3 <b>exampleUse.py -u </b> to see if the router is responsive

To make things work you need to make sure the <u>config.ini</u> file is up to date, rename the config_bak.ini file to config.ini and make sure your passwords and ip addresses are filled in correctly in the config.ini file
  
too run this command line program see the following examples
  
  <b>python3 fireControl.py -n</b> 
          <br>   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  or<br>
  <b>python3 fireControl.py host</b>
<h5><u>Comand line switch options</u></h5>  


-e or enable   &emsp;&ensp;&nbsp;&nbsp;   Enable Internet <br>
-d or disable   &emsp; &ensp;&nbsp; Disable the internet   
-c or configure &emsp;&nbsp;  Put the router in configuration mode <br>
-u or uptime   &emsp; &emsp;&nbsp;   Is the router up? <br>
-s or show    &emsp;&emsp;  &emsp;   Show the firewall rules<br> 
-x or exit    &emsp; &emsp;&emsp;&emsp;   Leave the configuration console?<br> 
-q or quit    &emsp; &emsp;&emsp;&ensp;&nbsp;   Leave and shut connection<br>
-n or host    &emsp; &emsp;&emsp;&ensp;   Router host name<br>

To taylor make this application, just look at expanding the methods in the fireControl.py
and the command line options in main py.

To use this out of pycharm, run the exampleUse.py this will return the host name from your router 

Note to myself:
to create a distro, run the setup.py
then run the run setup.py task from the tools menu and select sdist and in the options choose zip for the format, then 
distro for the folder name 

after this from the pycharm terminal rune the following : python setup.py bdist_wheel --universal
to make a wheel.

This makes a folder called dist with the configured wheel file.
wheel files can be installed using the pip3 install blahblah.whl
Hopefully if everything works then all the dependancies will be installed and the program will work on anything?
Just be mindful that the program needs the config.ini file make sure it is correctly configured and is present.

You can contact me at michael@duplessis.nz if you need a hand getting the thing to work.