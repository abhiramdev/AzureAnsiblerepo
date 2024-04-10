#Git commands: 
which git (ensure that git is installed in the machine) 
install git
create a new file containing list of servers 
add that file to git using :
git add <filename>
git commit -m <"Message ">
git push origin master/main


configure ansible.cfg
in that mention the path of inventory and also pvt key of ansible under [default]
eg : 
========
[defaults]
inventory = inventoryServerlist
private_key_file= ~/.ssh/ansible
========

then we can run ansible command in short hand form : 

eg : ansible all -m ping 

fullhand : ansible all ~/.ssh/ansible <inventoryfilename> -m <Module name>
