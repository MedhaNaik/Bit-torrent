#Description
A peer to peer application that can transfer torrent files between peers.

#Files required
peerProcess.java
Common.cfg
PeerInfo.cfg
thefile

#How to run:
We ran the program servers mentioned in the configuration files. Below are the steps for the same:

* Ensure that all the required files are available and that you are in the current directory.
* Ensure that "thefile" is present in the folders as required by the PeerInfo.cfg.
* Compile the program with: 
	- javac peerProcess.java
* Start each peer in ascending order in the server mentioned in PeerInfo.cfg using the command:
	- java peerProcess 1001
	where 1001 is the peer id.
The program terminates after all the peers have completed downloading the file fully.

#What is working?
All the functionalities as mentioned in the project description are working as expected. 
The following functionality as mentioned in the project description are working:

* Start peer process
	- Peer reads the Common.cfg and the PeerInfo.cfg and correctly sets the variables and the bitfields.
	- Peer connects to all other neighbors that started before it and waits for subsequent peers to connect.
	- Peer starts exchaging pieces once it is connected to atleast one other peer.

* After connection
	- Handshake is exchanged between the peers.
	- The peer sends its bitfield messages only if it has the file.
	- Peer sends the interested or uninterested message.
	- Peers send the choke and unchoke messages every 5 seconds after changing its preferred neighbors.
	- The optimistically unchoked messsage is updated every 10 seconds.

* File Exchange
	- Sends the request, have, not interested, interested, piece and on reception of the have messages 
	and updates the related bitfield.

* The program terminates after all the peers have completed downloading the file fully.

#Video url:
https://uflorida-my.sharepoint.com/:v:/g/personal/gkamathkoteshwar_ufl_edu/ERDIGT1uuORBn_MhiUT_K7gBp3FnuY3R89gNiTW0xB6kxQ?e=i8N0o7