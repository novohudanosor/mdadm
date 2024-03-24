# mdadm
mdadm
Из директории HWmdadm запускаем vagrant up
после up вирт машины vagrant ssh
mdadm --zero-superblock --force /dev/sd{b,c,d,e,f}    -  занулим супер блоки
mdadm --create --verbose /dev/md0 -l 6 -n 5 /dev/sd{b,c,d,e,f}  - создаем масси 6 из 5 устройств
mdadm -D /dev/md0  - проверям, создался ли массив.
создали конфигурационный файла mdadm.conf, который лежит /etc/mdadm/mdadm.conf  
создали партиции:
df -h
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        489M     0  489M   0% /dev
tmpfs           496M     0  496M   0% /dev/shm
tmpfs           496M  6.8M  489M   2% /run
tmpfs           496M     0  496M   0% /sys/fs/cgroup
/dev/sda1        40G  4.5G   36G  12% /
tmpfs           100M     0  100M   0% /run/user/1000
tmpfs           100M     0  100M   0% /run/user/0
/dev/md0p1      139M  1.6M  127M   2% /raid/part1
/dev/md0p2      140M  1.6M  128M   2% /raid/part2
/dev/md0p3      142M  1.6M  130M   2% /raid/part3
/dev/md0p4      140M  1.6M  128M   2% /raid/part4
/dev/md0p5      139M  1.6M  127M   2% /raid/part5
