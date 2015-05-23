# MITM_Toolkit

A toolkit for automating MITM attack management with ettercap.

## Incremental Poison

This shell script accepts 3 arguments. The interface you are using (eth1, eth2, etc...), the number of concurrent hosts you want to poison, and the name of a directory you want to output the packet captures to. 
When launched, it will open a separate gnome-terminal (so you have to do it in the desktop interface), and will start poisoning. To move to the next batch, just hit the 'q' button on that interface and it will gracefully shutdown, re-ARP the hosts (to prevent disruption), and then launch the next set. 
While this is happening, everything is being dumped into an organized collection of log files.
Currently the script assumes the gateway is on your /24 network (so should work out of the box 90% of the time). Will be updating to support more unusual cases as well. 
