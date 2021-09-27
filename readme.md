to see all the interfaces  `ifconfig`

to see through which interface the packets are transmitting 

`tcpdump -i *name of the interface*`

goto Kloudlab.org, log in, on the left bar click `cloud servers`

select `ubuntu 20.04` and hit `start the server`

after the server initiates, `download keypair`

now from terminal go to the folder where you downloaded the keypair and then 

`sudo chmod 400 *name of the keypair*`

`ssh -i *name of the keypair* ubuntu@*ip of the server*`

type `yes` and hit enter

boom , we are in one AWS server

`sudo apt update`

`sudo apt install docker.io`

`sudo systemctl restart docker`

`sudo systemctl status docker`

`sudo docker run -p 80:80 nginx`

now if we go to the server ip we can see the nginx default page.

`sudo apt install net-tools`

`ifconfig`

N.b.: 1.docker0 is the l2 bridge.

      2.veth.... is connected with the l2 bridge

`tcpdump -i *name of the interface*`

`tcpdump -i *name of the interface* dst port 80` only shows the packets that has destination port 80

`sudo docker ps`

`sudo docker exec -it *first 2 digit  of the container* sh`

now we are inside the container

`apt install net-tools`

`apt-get install -y tcpdump`

`tcpdump -i eth0`

N.b. everytime we use `tcpdump` we need to reload the server ip page in browser.

we can go to `bgp.he.net` and see that the ip matches the ip of source ip of the packets.

`sudo iptables -L` to see the iptables rules

`route` to see the route table of the namespace of host.

open another terminal and ping the ip of eth0 from there 

now go to the previous terminal and if we `tcpdump -i eth0` then we can see the packets transmitting.

try `route` from inside the container.