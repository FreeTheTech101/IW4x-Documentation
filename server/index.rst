.. todo::

   This page is still work in progress.

Server
======

Quick setup and advanced configuration for IW4x servers.

.. warning::

   You can only host up to 15 servers on the same IP address, additional
   servers will be rejected by the decentralized node system. This has been
   implemented as a security measurement to prevent flooding the server list.

Server types
------------

Party
~~~~~

A party [1]_ is a dedicated lobby, which uses a playlist for its
configuration and will take players back into a lobby after each map.
The advantage of the party system is:

-  adjust classes and killstreak rewards without leaving the server
-  vote to skip next map
-  map rotation is random

Because of that, a party server is ideal for a public game servers.

Match
~~~~~

A match is a normal dedicated server, which uses a map rotation, ideal
for private servers.

Requirements
------------

You have to fulfill the following requirements to be able to host a
server for IW4x:

-  An internet connection
-  A clean installation of `Call of Duty: Modern Warfare
   2 <http://store.steampowered.com/app/10180>`__
-  `Notepad++ <http://notepad-plus-plus.org>`__ to edit config files
-  `7-ZIP <http://www.7-zip.org>`__ to extract archives
-  Basic knowledge about your current operating system

Quick instructions for hosting a match server
---------------------------------------------

-  Copy your 'Call of Duty Modern Warfare 2' folder to another location
-  Extract the archive in your copied folder
-  Download the :download:`server.cfg <conf/match/server.cfg>` and place it
   in your 'players' folder
-  Download the :download:`startserver.bat <conf/match/startserver.bat>` and
   edit it
-  Forward the TCP and UDP port you put in ``+set net_port <port>``
-  Run the batch and have fun!

Quick instructions for hosting a party server
---------------------------------------------

-  Copy your 'Call of Duty Modern Warfare 2' folder to another location
-  Extract the archive in your copied folder
-  Download the :download:`server.cfg <conf/party/server.cfg>` and place it
   in your 'players' folder
-  Download the :download:`startserver.bat <conf/party/startserver.bat>` and
   edit it
-  Forward the TCP and UDP port you put in ``+set net_port <port>`` (UDP
   and TCP)
-  Run the batch and have fun!

Advanced server configuration
-----------------------------

Further information for advanced server configuration:

.. toctree::
   :maxdepth: 1
   :name: advanced_server_configuration

   General <general>
   Match server <match>
   Party server <party>

.. [1]
   A server starts per default as a party.
