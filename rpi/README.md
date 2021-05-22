# Configure Raspberry Pi

## How to find IP address

In terminal:
sudo nmap -sP 192.168.1.0/24 

Output:
```
Starting Nmap 7.80 ( https://nmap.org ) at 2021-05-08 13:32 MSK

Nmap scan report for netgateway (192.168.1.1) Host is up (0.0013s latency). MAC Address: 50:FF:20:0B:D4:9E (Keenetic Limited) 
Nmap scan report for 49.1.168.192.fryazino.net (192.168.1.49) Host is up (0.0018s latency). MAC Address: 50:FF:20:18:70:58 (Keenetic Limited) 
Nmap scan report for 61.1.168.192.fryazino.net (192.168.1.61) Host is up (0.086s latency). MAC Address: 0C:25:76:3A:FC:64 (Longcheer Telecommunication Limited)
**Nmap scan report for 67.1.168.192.fryazino.net (192.168.1.67) Host is up (0.038s latency). MAC Address: DC:A6:32:CF:94:AA (Raspberry Pi Trading)**
Nmap scan report for 101.1.168.192.fryazino.net (192.168.1.101) Host is up (0.0032s latency). MAC Address: 40:61:86:E3:9C:5E (Micro-star Int'l) 
Nmap scan report for 210.1.168.192.fryazino.net (192.168.1.210) Host is up (0.0033s latency). MAC Address: 3C:52:82:BC:42:D2 (Hewlett Packard) 
Nmap scan report for 53.1.168.192.fryazino.net (192.168.1.53) Host is up. Nmap done: 256 IP addresses (7 hosts up) scanned in 1.49 seconds
```
## How to enable SSH:

In **boot** chapter of SD card with RPi image:
* Create a file named “wpa_supplicant.conf” (remove any other extension like “.txt”).
* Open this file with any text editor (on Windows -> right click + “Open with”), and write the following:

```
country=US # replace with your country code
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
network={
    ssid="WIFI_NETWORK_NAME"
    psk="WIFI_PASSWORD"
    key_mgmt=WPA-PSK
}
```

https://roboticsbackend.com/enable-ssh-on-raspberry-pi-raspbian/#Enable_ssh_on_Raspberry_Pi_4_without_any_monitor
