## Notes 

You should be able to ssh to your remote ubuntu machine beforehand .Ubuntu comes with python installed.

The playbook ubuntu-ex-0.yaml uses the installation steps that are recreated from docker documentations : for ubuntu 20-04   https://docs.docker.com/engine/install/ubuntu/
Also  it used root for installation and creating and running containers.
This is for test . Its advicible to create a user that can execute docker commands.

The playbook ubuntu-ex-0.yaml  uses ansible role to install docker automatically   ```ansible-galaxy install geerlingguy.docker```
