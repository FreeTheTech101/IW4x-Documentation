.. todo::

   This page is still work in progress.

Advanced party server configuration
===================================

This is how you configure your server to run as a party server.

Server config
-------------

This part of the configuration has to be done in the server.cfg file
that your server is using. Please put your server configuration file in
the ``players`` folder in your MW2 root directory.

`General <general.html>`__ server configuration is required for general
configuration options.

Info
~~~~

+----------------------------------+-----------------+-----------+---------------------------------------------------------------------------+
| parameter                        | default         | valid     | description                                                               |
+==================================+=================+===========+===========================================================================+
| ``set sv_hostname <string>``     | "IW4x Server"   |           | Sets the server hostname                                                  |
+----------------------------------+-----------------+-----------+---------------------------------------------------------------------------+
| ``set sv_securityLevel <int>``   | 23              | 0 - 256   | Configures the servers security level                                     |
+----------------------------------+-----------------+-----------+---------------------------------------------------------------------------+
| ``set sv_motd <string>``         |                 |           | Sets a custom motd which is shown on the loadscreen when a player joins   |
+----------------------------------+-----------------+-----------+---------------------------------------------------------------------------+
| ``sets _Admin <string>``         |                 |           | Configures admin name                                                     |
+----------------------------------+-----------------+-----------+---------------------------------------------------------------------------+
| ``sets _Email <string>``         |                 |           | Configures admin email                                                    |
+----------------------------------+-----------------+-----------+---------------------------------------------------------------------------+
| ``sets _Website <string>``       |                 |           | Configures website                                                        |
+----------------------------------+-----------------+-----------+---------------------------------------------------------------------------+
| ``sets _Location <string>``      |                 |           | Configures location                                                       |
+----------------------------------+-----------------+-----------+---------------------------------------------------------------------------+

Non gameplay configuration
~~~~~~~~~~~~~~~~~~~~~~~~~~

+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| parameter                                 | default              | valid      | description                                                    |
+===========================================+======================+============+================================================================+
| ``set rcon_password <string>``            | ""                   |            | Configures password for rcon                                   |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set g_password <string>``               | ""                   |            | Configures password for gameserver                             |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set g_inactivity <int>``                | 120                  | 0 - 999    | Enable auto kick feature for idle/AFK players                  |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set g_inactivitySpectator <int>``       | 180                  | 0 - 999    | Time in seconds before a spectator gets kicked                 |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set g_logSync <int>``                   | 1                    | 0 - 1      | 1 = always flush games\_mp.log, 0 = only flush on game end     |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set g_log <string>``                    | logs/games\_mp.log   |            | Configures gamelog filename                                    |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set sv_allowClientConsole <int>``       | 1                    | 0 - 1      | Enable players ability to access server commands               |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set sv_maxPing <int>``                  | 0                    | 0 - 999    | Maximum ping allowed, any higher and players will get kicked   |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set sv_timeout <int>``                  | 20                   | 0 - 1800   | Timeout time period                                            |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set sv_reconnectlimit <int>``           | 3                    | 0 - 1800   | How many times you can try to reconnect                        |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set sv_pure <int>``                     | 0                    | 0 - 1      | Verifying client files                                         |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set sv_sayName <string>``               | ^7Console            |            | Name server-side 'say' commands show up as                     |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set sv_floodProtect <int>``             | 1                    | 0 - 1      | Chat Spam Protection                                           |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set sv_kickBanTime <int>``              | 300                  | 0 - 3600   | Configures kick ban duration                                   |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set scr_game_objectiveStreaks <int>``   | 1                    | 0 - 1      | Enable Chopper, AC130 and Nuke                                 |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set scr_classic <int>``                 | 0                    | 0 - 1      | Enable IW3 killstreak system                                   |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+
| ``set scr_intermission_time <int>``       | 30                   | 0 - 999    | Change timer before server loads the next map                  |
+-------------------------------------------+----------------------+------------+----------------------------------------------------------------+

Required mod configuration has to be done in this file as well.

Playlist config
---------------

The following configuration has to be done in your playlist. Do not edit
your ``iw4x/playlist_default.info`` file directly as this file is
updated via the updater and will be resetted to defaults.

Instead put your playlist in the ``players`` folder in your MW2 root
directory.

General
~~~~~~~

Playlists are limited to 32 Gametypes and 23 playlists. It is possible
to create multiple seperate playlists. A single server can only run a
single playlist at a time.

Function script
~~~~~~~~~~~~~~~

In playlists you can use the following parameters to configure your game
server:

-  ``gametype <string>``: Unique name for your configured gametype.
   Everything until the next gametype configures your gametype.
   Eg.: ``gametype tdm``
-  ``name <string> "<string>"``: Configures a specific localized name
   for the gametype which is shown to the user.
   Eg.: ``name english "Team Deathmatch"``
-  ``script``: Gametype the game actually loads.
   Eg.: ``script war``
-  More gametypes can be found
   `here <general.html#supported-gametypes>`__
-  ``teambased``: Currently unknown
-  ``hardcore``: Currently unknown
-  ``rule <string> <string>``: Rule is used to customize dvars.
   Eg.: ``rule scr_thirdperson 0``
-  For possible values you can check the options for your preferred
   gametype `here <party.html>`__

Playlist
~~~~~~~~

The first playlist in your file has to be ``playlist 1``. To start this
playlist on your server, you have to pass the parameter
``+set playlist 0``.

-  ``playlist <int>``: Configures playlist
-  ``rule <string> <string>``: Overwrites rules configured in your
   function.
-  ``<mapname>,<gametype>,<mapweight>``: Configures your playlist. Put
   every map you want in your map rotation on a seperate line. The
   higher the mapweight the more likely this map will be picked.
   Eg.: ``mp_rust,tdm,4`` or ``mp_fuel2,tdm,1``
