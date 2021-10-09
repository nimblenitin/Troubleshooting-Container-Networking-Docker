# Troubleshooting-Container-Networking-Docker

Steps to troubleshoot container networking in different ways-

```

1. Create an ubuntu container
$ sudo docker run -t -d --name container1 ubuntu:latest

2. List all the running containers
$ sudo docker ps

3. Use the following command to inspect a container:
$ sudo docker inspect container1

4. Troubleshooting using network troubleshoot tools like nicolaka or netshoot. Use the following command to troubleshoot host network:
$ sudo docker run -it --net host nicolaka/netshoot

5. Use nsenter to enter any namespace with netshoot running as a privileged container
#running netshoot in privileged mode
$ docker run -it --rm -v /var/run/docker/netns:/var/run/docker/netns --privileged=true nicolaka/netshoot

Note: The following commands can be used inside network namespace for troubleshooting:
ifconfig		#interface list
brctl show		#bridge list
ip route show		#route table
bridge fdb show	#encapsulation detail
ipvsadm		#load balancing

```
