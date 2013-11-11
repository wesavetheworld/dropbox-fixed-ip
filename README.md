# dropbox-fixip 
=============

This scripts allows anybody to track their remote computer's IP from anywhere, like having a fix IP, through dropbox Public folder.

## How it works. 

  In the remote machine is running the daemon:  track_ip, and the daemon control
  script the track_ip_service. 
  
  track_ip : Will save the computer external IP address in the ~/Dropbox/Public/ip_machine_home and
             and ~/Dropbox/Public/ip_machine_home.html in 15 minute time interval that can be adjusted by the user.
             It'll also print the URL of the files:  ip_machine_home and ip_machine_home.html
             
              ip_machine_home - Has the code:
              MY-CURRENT-IP
             
              ip_machine_home.html - Has the code html:
              http://MY-CURRENT-IP:MY-HTML-PORT
             
                For example:
                
                Link http: Remote Machine Server1
                External IP: 54.17.98.159
                Internal IP: 192.168.1.27
                
              By this way it's possible to access the computer's html server from anywhere in the world.
  
  
The script connect-remote  run in the local/client machine.  It's needed to set the connect-remote script. By changing
the USER="mrdummy" your ssh user and  track_url= "https://dl.dropboxusercontent.com/u/852234567/ip_machine_home"
to your file public url.
    
This script downloads the file  "ip_machine_home" using curl. Extracts the IP and connect to required port.


## Usage

### Remote Machine
  1. Install Dropbox
  2. Put  track_ip track_ip_service in the  same folder
  3. chmod +x track_ip_service
  4. ./track_ip_service start
  5. ./track_ip_service status


### Client Machine
Usage:

  1. Edit the   connect-remote script as described above.
  2. chmod +x connect-remote script
  3. ./connect-remote  update  
  4. ./connect-remote  ssh    
  5. OR  ./connect-remote  sftp     
   


Enjoy !!! Modify ! Run test at will!!!
