# Final-Project-WiFi-Jammer-Deauth-Attack

For the final project, I wanted to include all devices acquired throughout the course and put them to use (raspberry pi, kali linux, wireless card with packet injection capabilities).

I will be presenting a WiFi jamming python script which continuously identifies all access points and their respective clients on channels 1-11, sends deauthentication packets and kicks them off the network. I will also show how to manually deauthenticate a client from an AP using terminal commands in Kali Linux. 

Sources: https://github.com/DanMcInerney/wifijammer/blob/master/wifijammer.py

Commands I used to monitor networks in my range are:

1. "airodump-ng wlan0mon(your monitoring interface)" - lists the MAC address of the router, SSID, and channel, as well as stations (clients on respective networks).

2. "airodump-mg --channel 2(channel of network you would like to monitor) --bbsid E0:00:00:00:00:00(MAC address of router) wlan0mon(your monitoring interface)" - This filters network traffic, so you can view the MAC address of clients you'd specifically like to kick off.

3. "aireplay-ng --deauth(Type of packet) 100(Amount of packets) -a E0:00:00:00:00:00(AP) -c E0:00:00:00:00:00(client) wlan0mon" - aireplay-ng is a command used to inject packets. This command send is sending deauth packets from the router your pretending to be, to its client, essentially kicking off the client.
