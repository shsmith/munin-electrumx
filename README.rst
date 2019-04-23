
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

Install munin and apache2.  For Ubuntu systems the commands are::

    sudo apt-get update 
    sudo apt-get install munin apache2

The electrumx_bw plugin uses nethogs. To install it::

    sudo apt-get install nethogs

Once you have munin up and running, add the following files::

 /etc/munin/plugins/
    bitcoin_blocks
    bitcoin_bw  
    bitcoin_conn
    bitcoin_diff
    bitcoin_du
    bitcoin_fee
    bitcoin_mempool
    bitcoin_mp
    bitcoin_mp2
    bitcoin_peer_versions
    bitcoin_ticker
    bitcoin_ticker_bch
    bitcoin_ticker_bchsv
    bitcoin_tx
    bitcoin_vm
    electrumx_bw
    electrumx_caches
    electrumx_client_protocol
    electrumx_client_versions
    electrumx_connrate
    electrumx_err
    electrumx_io
    electrumx_lsof
    electrumx_mem
    electrumx_peers
    electrumx_peer_versions
    electrumx_reqcounts
    electrumx_ses
    electrumx_sub
    electrumx_tx
    electrumx_users

These plugins require configuration. 
The configurations are in the following files added to your plugin-conf.d folder.::

 /etc/munin/plugin-conf.d/
    bitcoin
    electrumx

You will need to edit /etc/munin/plugin-conf.d/bitcoin. 
*******************************************************

- Adjust the ``BITCOIN_DATADIR`` environment to specify where to find your bitcoin data directory.
- Adjust the ``BITCOIN_CLI`` environment to specify where to find bitcoin-cli.
- Adjust the ``ELECTRUMX_DATADIR`` environment to specify where to find your electrumx data directory.

You will need to edit /etc/munin/plugin-conf.d/electrumx. 
*********************************************************

- Adjust the ``ELECTRUMX_RPC`` environment to specify where to find electrumx_rpc.py.

You will need to make the munin plugins executable.
***************************************************

The munin plugins must be marked as executable.
You can do so using this command::

    sudo chmod +x /etc/munin/plugins/*

After configuring the plugins, restart the munin-node service.

Versions
--------

These plugins are working with the following software versions::

 Operating System:   Ubuntu 18.04
 Munin-Node:         2.0.25
 ElectrumX:          1.11.0
 Bitcoin Core:       0.17.1
 Bitcoin ABC:        0.18.4
 Bitcoin SV:         0.1.0

Live Example
------------

You can see these plugins in action here:
    http://vps.hsmiths.com:49001/munin/hsmiths.com/vps.hsmiths.com/


=======================================================

**Samuel Smith**  shsmith@socal.rr.com   https://github.com/shsmith

Tip jar: 1CspNS6AFsDbqiocsvqpjiMPrtviRCaXz5
