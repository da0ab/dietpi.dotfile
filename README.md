# dietpi.dotfile
dietpi dot file

```
       /██ /██             /██               /██           /██             /██      /██████  /██ /██          
      | ██|__/            | ██              |__/          | ██            | ██     /██__  ██|__/| ██          
  /███████ /██  /██████  /██████    /██████  /██      /███████  /██████  /██████  | ██  \__/ /██| ██  /██████ 
 /██__  ██| ██ /██__  ██|_  ██_/   /██__  ██| ██     /██__  ██ /██__  ██|_  ██_/  | ████    | ██| ██ /██__  ██
| ██  | ██| ██| ████████  | ██    | ██  \ ██| ██    | ██  | ██| ██  \ ██  | ██    | ██_/    | ██| ██| ████████
| ██  | ██| ██| ██_____/  | ██ /██| ██  | ██| ██    | ██  | ██| ██  | ██  | ██ /██| ██      | ██| ██| ██_____/
|  ███████| ██|  ███████  |  ████/| ███████/| ██ /██|  ███████|  ██████/  |  ████/| ██      | ██| ██|  ███████
 \_______/|__/ \_______/   \___/  | ██____/ |__/|__/ \_______/ \______/    \___/  |__/      |__/|__/ \_______/
                                  | ██                                                                        
                                  | ██                                                                        
                                  |__/
 ```

### Вход ssh
```
ssh root@DietPi.local
http://192.168.0.1/
ssh root@192.168.0.106
```

```
ssh-keygen -f "/home/da0ab/.ssh/known_hosts" -R "192.168.0.106"
```

### Апдейт и настройки
```
dietpi-config
dietpi-update
```
  
#### dietpi.txt.
````
# Включаем WiFi (строго 1)
AUTO_SETUP_NET_WIFI_ENABLED=1
# Отключаем Ethernet, чтобы не мешал
AUTO_SETUP_NET_ETHERNET_ENABLED=0
# Код страны (RU, GB, DE и т.д.)
AUTO_SETUP_NET_WIFI_COUNTRY_CODE=RU
# Включаем автоматическую настройку 
AUTO_SETUP_AUTOMATED=1
```

#### dietpi-wifi.txt.

```
aWIFI_SSID[0]=''
aWIFI_KEY[0]=''
aWIFI_KEY_MGR[0]='WPA-PSK'
aWIFI_CONF_FILE[0]=''
AUTO_SETUP_NET_WIFI_COUNTRY_CODE=RU
```


### Дисплей
```
curl -L -o waveshare35a.dtbo https://raw.githubusercontent.com/waveshare/LCD-show/master/waveshare35a-overlay.dtb
```    

    
### Правка руками конфига после установки
``
rootfs/etc/wpa_supplicant/wpa_supplicant.conf.
``

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=RU

network={
    ssid=""
    psk=""
    key_mgmt=WPA-PSK
    scan_ssid=1
}
```

## Красоты 

```
sudo apt install fonts-terminus
sudo dpkg-reconfigure console-setup
sudo dietpi-banner
```

``
10  Custom banner entry
``
### kbd
    
````
sudo vim /etc/rc.local

перед exit 0:
setvtrgb 2E3440 BF616A A3BE8C EBCB8B 81A1C1 B48EAD 88C0D0 E5E9F0 4C566A BF616A A3BE8C EBCB8B 81A1C1 B48EAD 8FBCBB ECEFF4
````    
    
``    
sudo vim /etc/issue
``


```

\e[H\e[2J
\e[1;36m
     ██╗███████╗██╗
     ██║╚══███╔╝██║
 ██████║  ███╔╝ ██████╗
██╔══██║ ███╔╝  ██╔══██╗
 ██████║███████╗██████╔╝
 ╚═════╝╚══════╝╚═════╝ \e[0m \e[1;37m
------------------
\4
------------------ \e[0m
```
    
    
 

