# nso-ansible-installation
## Description
Recently I installed NSO in few customers environments and I thought it would be helpful to automate the installation procedures instead of repeating it each time or PoC.
 
So I wrote Ansible module that take three inputs from user and take care of the rest

## File Input
| variable name        | usage                                                                                           |
|----------------------|-------------------------------------------------------------------------------------------------|
| ncs_package_name     | This is the name of NSO downloaded package (example: nso-4.4.linux.x86_64)                      |
| ncs_package_location | Where you uploaded this package in linux server(example: /root/)                                |
| ncs_run_location     | The location of instantiated project from NSO installation (example: ncs-run or access_project) |


Once you run the module (locally or via remote host), it will prepare the linux machine first with some settings (like disable selinux and firewalld services, install correct java version, update the cache..etc) then customize the bash profile with ncsrc file and finally install and run the NSO at the end

to run it, simply execute the below command on host that has ansible package installed

## Commands
```
#ansible-playbook nso_demo.yml
```

if you need to run it in verbose mode to see the exact running commands, then add few "vvv" to the command

```
#ansible-playbook nso_demo.yml -vvv
```
