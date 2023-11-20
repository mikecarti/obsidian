#restart #vbox #copy-paste:
pkill VBoxClient (or "ps aux www | grep VBoxClient -- && ki>
VBoxClient-all


#show #overall #disk #storage #space :
df

#get #size #directory:
du -sh file_path

#size #file :
du -h filename

#cd #back:
cd -

#docker #eat #space #nospace #disk:
```
docker system prune -a
```

#show #graphics #card #gpu
```
lspci
sudo lshw -C display
```


#Remove #keybind:
```
gsettings list-recursively | grep ......
gsettings set XXX.XXXXXX.XXXXX.XXX xxxxxx []
```

#Make #screen #clickable #again:
```
pkill VBoxClient (or "ps aux www | grep VBoxClient -- && kill -9 PID")
VBoxClient-all
```


#Intellij:

# Disable linux latency:
vm_options -> type command: -Dsun.java2d.metal=false


# [[Git commands]]

# [[Virtual Environment]]
