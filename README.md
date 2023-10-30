# kill_connection_when_other_is_activated
Network Manager Dispatcher automatically enable WLAN when the LAN connection is disconnected and disable WLAN when a LAN connection is established.

STEP ONE:
open the commandline an create a new .sh file with following command:
nano /etc/network/if-up.d/wlan-off

STEP TWO:
fill in following lines:

#!/bin/bash
if [ "$IFACE" = "eth0" ]; then
    /sbin/ifconfig wlan0 down
fi


STEP THREE:
close NANO with CTRL+S and CRTL+X

STEP FOUR:
set exec rights:
chmod +x /etc/network/if-up.d/wlan-off

STEP FIVE:
reboot the networking service:

systemctl restart networking


when you have questions, contact me on X / Twitter ( @06druese08 )
