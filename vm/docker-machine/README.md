## Notes 
docker-machine is provsion tool used,In this lab used to create vm running on tinycore with docker installed with other tools.

To create vm using docker-machine 
```
docker-machine create -d hyperv --hyperv-virtual-switch "PVS" node1
```
to ssh to that machine use
```
ssh docker@ip-node1 
```
or 
```
docker-machine ssh node1 
```
Basic informations about node1 variables : ssh_username and ssh_pass and port 
```
docker_machine_name=node1
docker_ssh_user=$(docker-machine inspect $docker_machine_name --format={{.Driver.SSHUser}})
docker_ssh_key=$(docker-machine inspect $docker_machine_name --format={{.Driver.SSHKeyPath}})
docker_ssh_port=$(docker-machine inspect $docker_machine_name --format={{.Driver.SSHPort}})
```
To change the password , ssh to node1 
```
sudo vi var/lib/boot2docker/profile 
```
And add this  
```
echo "docker:newPassword"|sudo chpasswd
```

tinycore doesnt not haven python install , to execute ansible command, so its imporant execute 
```
tce-load -wi  python3.6
sudo pip3 install docker

```