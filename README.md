# Manually install  
```
wget -P /usr/bin/ https://github.com/vpslinuxinstall/Filebrowser/releases/download/v1.0/filebrowser        
cd /usr/bin/
chmod +x filebrowser
filebrowser --port 8300 
```        
Open your browser to `localhost:8300`.        

nano /lib/systemd/system/[filebrowser.service](https://github.com/vpslinuxinstall/Filebrowser/blob/master/filebrowser.service)  
```
nano /lib/systemd/system/filebrowser.service
Description=Filebrowser Service  
After=network.target  
Wants=network.target  

[Service]  
Type=simple  
PIDFile=/var/run/filebrowser.pid  
ExecStart=/usr/bin/filebrowser -c /etc/filebrowser/filebrowser.json  
Restart=on-failure  

[Install]  
WantedBy=multi-user.target
```









nano /etc/filebrowser/[filebrowser.json](https://github.com/vpslinuxinstall/Filebrowser/blob/master/filebrowser.json)  
```
nano /etc/filebrowser/filebrowser.json
{  
  "port": 8300,  
  "noAuth": false,  
  "baseURL": "/admin",  
  "address": "0.0.0.0",  
  "reCaptchaKey": "",  
  "reCaptchaSecret": "",  
  "database": "/etc/filebrowser/database.db",  
  "log": "stdout",  
  "plugin": "",  
  "scope": "/",  
  "allowCommands": true,  
  "allowEdit": true,    
  "allowNew": true,  
  "commands": [  
    "git",  
    "svn"  
  ]  
}
```
















download [filebrowser](https://github.com/vpslinuxinstall/Filebrowser/blob/master/filebrowser) to /usr/bin/  
```
cd /usr  

cd bin    

wget https://github.com/vpslinuxinstall/Filebrowser/blob/master/filebrowser

  
systemctl enable filebrowser    
systemctl start filebrowser
```








<br>








</br>







     
# Automatically install      
```
wget https://github.com/vpslinuxinstall/Filebrowser/raw/master/filebrowser.sh
  
chmod +x filebrowser.sh  
./filebrowser.sh
```




































