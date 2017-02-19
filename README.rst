
Munin-Node plugin to monitor ElectrumX and Bitcoin
--------------------------------------------------

These Munin-Node plugins gather data from your running instance of 
ElectrumX server and/or Bitcoin daemon.

ElectrumX server: 
    https://github.com/kyuupichan/electrumx
    
Bitcoin daemon:
    https://github.com/bitcoin/bitcoin
    

Getting Started
---------------

Install munin-node and apache2.
For Ubuntu systems the commands are:

|    sudo apt-get update 
|    sudo apt-get install munin apache2

Once you have munin up and running, add the following files:

| /etc/munin/plugins/
|    bitcoin_conn
|    bitcoin_fee
|    bitcoin_mp
|    bitcoin_mp2
|    bitcoin_vm
|    electrumx_err
|    electrumx_lsof
|    electrumx_mem
|    electrumx_peers
|    electrumx_ses
|    electrumx_sub
|    electrumx_tx

You will need to edit each of the bitcoin_* plugin files to specify your 
actual bitcoin data directory.    

The bitcoin_vm and electrumx_lsof plugins both require additional 
permissions in order to inspect the running processes. These permissions 
are granted by the corresponding files added to your plugin-conf.d folder.

| /etc/munin/plugin-conf.d/
|    bitcoin_vm
|    electrumx_lsof
    
After configuring the plugins, restart the munin-node service.


Versions
--------

These plugins are working with the following software versions:

| Operating system:    Ubuntu 16.04
| Munin-Node:          2.0.25
| ElectrumX:           0.11.4
| Bitcoin Core:        0.13.2


Live Example
------------

You can see these plugins in action here:
    http://vps.hsmiths.com:49001/munin/hsmiths.com/vps.hsmiths.com/


=======================================================

**Samuel Smith**  shsmith@socal.rr.com   https://github.com/shsmith

1CspNS6AFsDbqiocsvqpjiMPrtviRCaXz5
