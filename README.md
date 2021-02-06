# swarm-ansible

It make servers easy for struct docker swarm cluster with glusterfs

## Inventry
example
```
[docker]
192.168.122.60 ansible_become_pass=user
192.168.122.70 ansible_become_pass=user docker_swarm_join_to=192.168.122.60
192.168.122.70 ansible_become_pass=user docker_swarm_join_to=192.168.122.60

[gluster_server]
192.168.122.60 ansible_become_pass=user gluster_server="[{'brick_path': '/external_brick_test', 'nodes': ['192.168.122.60','192.168.122.70','192.168.122.80']}]"
192.168.122.70 ansible_become_pass=user gluster_server="[{'brick_path': '/external_brick_test', 'nodes': ['192.168.122.60','192.168.122.70','192.168.122.80']}]"
192.168.122.80 ansible_become_pass=user gluster_server="[{'brick_path': '/external_brick_test', 'nodes': ['192.168.122.60','192.168.122.70','192.168.122.80']}]"

[gluster_client]
192.168.122.60 ansible_become_pass=user gluster_client="[{'path': '/external_brick_test_client', 'src': 'localhost:external_brick_test'}]"
192.168.122.70 ansible_become_pass=user gluster_client="[{'path': '/external_brick_test_client', 'src': 'localhost:external_brick_test'}]"
192.168.122.80 ansible_become_pass=user gluster_client="[{'path': '/external_brick_test_client', 'src': 'localhost:external_brick_test'}]"
```
