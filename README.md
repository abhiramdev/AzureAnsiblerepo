Task1: Ansible 
----------

ssh-keygen -t ed25519 -C "<comment regarding the key>"
give the path (Defaule : ./.ssh/ed25519 ) and password for key generated
2 Keys will be created : ed25519(Highly confidential, donot expose) and ed25519.pub( no issue in displayinng )




Task2: GITPlay
===============
create repo
add ssh keys in settings
navigate to public key and copy contents to ssh keys. 

Git commands: 
-------------
which git (ensure that git is installed in the machine) 
install git
create a new file containing list of servers 
add that file to git using :
git add <filename>
git commit -m <"Message ">
git push origin master/main


Task3: 
========
configure ansible.cfg
in that mention the path of inventory and also pvt key of ansible under [default]
eg : 
========
[defaults]
inventory = inventoryServerlist
private_key_file= ~/.ssh/ansible
========

Task4: 
---------
then we can run ansible command in short hand form : 

eg : ansible all -m ping 

fullhand : ansible all ~/.ssh/ansible <inventoryfilename> -m <Module name>




