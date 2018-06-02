* to install Docker swarm container:

```docker run swarm --help```

* To run the consul container on the manager node:

```docker run -d -p 8500:8500 --name=consul progrium/consul -server -bootstrap```

* To run the swarm manage node on the master:

```docker run -d -p 4000:4000 swarm manage -H :4000 --advertise 192.168.0.248:4000 consul://192.168.0.248:8500 ```

* To run swarm join on the agent2

```docker run -d swarm join --advertise=192.168.0.246:2375 consul://192.168.0.248:8500```

* To run swarm join on the agent3
 
```docker run -d swarm join --advertise=192.168.0.247:2375 consul://192.168.0.248:8500```

* see cluster status

```docker -H :4000 info```

* Run on a container on your swarm cluster:

```docker -H :4000 run -p 3000:3000 -d wardviaene/nodejs-demo```

* List containers:

```docker -H :4000 ps```

* Connect to the nodejs-demo container

```curl 192.168.0.247:3000```

