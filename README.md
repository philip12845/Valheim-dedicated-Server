# Valheim-dedicated-server-
shell scripts for Debian based systems to start and update valheim dedicated server without opening the steam tool.
all of this requires valheim dedicated server to be installed on steam so install that first

how to install valheim dedicated server:
go to https://developer.valvesoftware.com/wiki/SteamCMD
install relevant version for your operating system 
then go to https://valheim.fandom.com/wiki/Valheim_Dedicated_Server and ignore all of their scripts
in valheim.sh you will need the following script :

  #!/bin/sh 
  export templdpath=$LD_LIBRARY_PATH  
  export LD_LIBRARY_PATH=./linux64:$LD_LIBRARY_PATH  
  export SteamAppID=892970

  echo "Starting server PRESS CTRL-C to exit"  
  ./valheim_server.x86_64 -name "<Philip>" -port 2456 -nographics -batchmode -world "<Philip1>" -password "you dont need these <> for the password" -public 1  
  export LD_LIBRARY_PATH=$templdpath

  #notes you can find in the valheim dedicated server directory under start_server.sh that script doesnt dogshit work tho but its useful to know the passowrd requirements and the ports needed
  # Tip: Make a local copy of this script to avoid it being overwritten by steam.
  # NOTE: Minimum password length is 5 characters & Password cant be in the server name.
  # NOTE: You need to make sure the ports 2456-2458 is being forwarded to your server through your local router & firewall.
  
  
installupdate.sh:
  in InstallUpdate.sh you will need the following script:
  steamcmd +@sSteamCmdForcePlatformType linux +force_install_dir /path/to/server +login anonymous +app_update 896660 validate +quit #!/bin/sh
  
Tip:
  run the InstallUpdate.sh file everytime the game updates make sure to exit your server before running this
