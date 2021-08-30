# linux command
ubuntu,centos, lib command 

## part
- [server resource](#server-resource)
- [tar](#tar)
- [system check](#system-check)
- [paraller](#paraller)
- [screen](#screen)
- [lftp](#lftp)
- [ffmpeg](#ffmpeg)


### server resource
*check mainboard*
```
dmidecode -t 2
```

*check memory*
```
lshw -class memory
```

*check cpu*
```
cat /proc/cpuinfo 
```
*check gpu*
```
#installed nvidia drive
nvidia-smi
```

### tar
*paraller*
```
tar zcvf - [dir] | pigz -9 -p [process] > [fname].tar.gz
```

### system check
*HDD badsector*
```
badblocks -v [path : /dev/sda10] > [log.txt]
```

*clean swap memory*
```
swapoff -a && swapon -a
```
### paraller
*xargs*
```
find ./ -name "*.pcm" | xargs -I{} -P[paraller num] bash -c ' echo {} ' {};

#example
find /data/youtube/videonew -name *.mp4 | xargs -I {} bash -c 'ffmpeg -i "$0" -ar 16000 -af "pan=mono|c0=c1" "${0/mp4/wav}" -y' {} ;
```

### screen
*screen escape(detach)*
```
ctrl a+d
```

*check screen list*
```
screen -list
```

*new screen session*
```
screen -S [session name] 
```
*screen attach*
```
screen -r [session name]
```

*screen already attach session access*
```
screen -r -x [session name]
```
*screen delete*
```
screen -X -S [screen name] kill
```

### lftp
*local command*
```
local ls
local cd
```
*lftp connect*
```
lftp -u [host] sftp://[ip]

```
*multi upload*
```
mirror --reverse -P [num of job] [data_dir]
```


