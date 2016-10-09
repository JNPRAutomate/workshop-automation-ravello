# Automation Workshop on Ravello  

This project will help to create and manage virtual topologies on Ravello that can
be used for training and workshop

# Dependencies

This project is leverating the roles [ravello-ansible](https://github.com/Juniper/ravello-ansible) to interact with Ravello

# Define a virtual topology

A virtual topology is define by an `inventory` file and a `topology` file.

A topology with 3 vqfx in triangle and 1 ubuntu server is defined by:
- inv-3vqfx-triangle.ini
- topology-3vqfx-triangle.yaml

> it's possible to have multiple topologies define in different files

# User Guide



# To create an application from Scratch

```
ansible-playbook -i inv-3vqfx-triangle.ini pb.rav.app.create.yaml --forks=1
```

To deploy and start VMs
```
ansible-playbook -i inv-3vqfx-triangle.ini pb.rav.app.deploy.yaml
```
> it's possible to only start some VM by using the option --limit

To collect all fqdn and populate the variable `ansible_ssh_host`

```
ansible-playbook -i inv-3vqfx-triangle.ini pb.rav.app.get_fqdn.yaml
```


To install all automation tools on the server(s)
```
ansible-playbook -i inv-3vqfx-triangle.ini pb.server.setup.yaml
```
