# tcpkit
A tool analyze tcp packets with Lua.

## How to use

```
./tcpkit
    -s server ip.
    -p port.
    -i device.
    -S lua script path, default is ../scripts/example.lua.
    -l local address.
    -C calculate bandwidth mode.
    -d duration, take effect when -C is set.
    -f log file.
    -v version.
    -h help.
```

### install 

```shell
$ cd tcpkit/src
$ make
```

### calculate port bandwidth

```shell
$ ./tcpkit -p 11211 -i en5 -C -d 10
```

calculate server bandwidth every 10 seconds.

### how to acquire device

use `ifconfig`

### capture packet

```
sudo ./tcpkit -S ../scripts/example.lua -p 5555 -i en5 -s 192.168.1.2
```

### Monitor redis or memcached cost time 

```
sudo ./tcpkit -S ../scripts/redis_mc_monitor.lua -p 6379 -i en5 -s 192.168.1.2
```
![image](https://raw.githubusercontent.com/git-hulk/tcpkit/master/snapshot/redis_mc_monitor.png)


### Monitor Kafka cost time

```
sudo ./tcpkit -S ../scripts/kafka_monitor.lua -p 6379 -i en5 -s 192.168.1.2
```
