> find / -type f -size +200M

> grep 'tom' info.log| awk -F ',' '{print $4}' |sort |uniq -c
