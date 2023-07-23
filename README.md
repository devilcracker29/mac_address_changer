# mac_address_changer
you can easily change your MAC address in your Device.

SOURCE CODE

import subprocess
import time
subprocess.call("ifconfig")
interface=input("\n[*]Enter Interface (etho or wlan or esn33) : ")
new_mac=input("[*]Enter New MAC Address : ")
print("\n[*]Changing Mac Address "+interface+" To "+new_mac)
print("\nSHUTING down the Device Network Drive.\n[*]wait for few seconds..... ")
time.sleep(10)
subprocess.call(["ifconfig",interface,"down"])
print("\n[*]Now this Divice Network has Disconnected\n")
subprocess.call(["ifconfig",interface,"hw","ether",new_mac])
time.sleep(5)
print("\n[*]Your Device MAC Address has Changed to "+new_mac)
print("\n[*]Restarting Your Device Network Drive.\n[*]wait for few seconds.....")
time.sleep(10)
subprocess.call(["ifconfig",interface,"up"])
subprocess.call("ifconfig")
print("\n[*]Now Your Device is ready to use with New MAC Address\n")
print("**********************GOOD BEY**********************")
