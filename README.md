# MITM_Toolkit

A toolkit for automating MITM attack management with ettercap.

This is a collection of scripts to assist with MITM attacks. While this does constitute my best efforts to streamline these attacks, most of the thanks is still owed to Alberto Ornaghi, Marco Valleri, Emilio Escobar, and Eric Milam for the authorship and/or continued support of Ettercap, as well as Laurent Gaffie for PCredz. Without these tools, my scripts wouldn't get you very far.

## Incremental Poison

This shell script accepts 3 arguments. The interface you are using (eth1, eth2, etc...), the number of concurrent hosts you want to poison, and the name of a directory you want to output the packet captures to. When launched, it will open a separate gnome-terminal (so you have to do it in the desktop interface), and will start poisoning. To move to the next batch, just hit the 'q' button on that interface and it will gracefully shutdown, re-ARP the hosts (to prevent disruption), and then launch the next set. While this is happening, everything is being dumped into an organized collection of log files. Currently the script assumes the gateway is on your /24 network (so should work out of the box 90% of the time). Will be updating to support more unusual cases as well. 

## Pcap Parser

This shell script accepts 1 argument. The argument describes the path to the output directory from Incremental Poison, which contains all of the pcap files from a poisoning attack. It passes these pcaps through Ettercap -r and PCredz to extract credentials from the captured traffic.
