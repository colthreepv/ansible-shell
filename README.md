ansible-shell
=============
[![Docker Automated build](https://img.shields.io/docker/automated/colthreepv/ansible-shell.svg?style=for-the-badge&maxAge=3600)]()
[![Docker Pulls](https://img.shields.io/docker/pulls/colthreepv/ansible-shell.svg?style=for-the-badge&maxAge=600)]()  

autobuilt docker container to execute [Ansible][3] in a control role with auto-completion

This docker container let's you execute an [Ansible][3] shell with Bash and kubectl completion.  
Refer to [williamyeh/ansible][1] for [all possible settings][2]

[1]: https://github.com/William-Yeh/docker-ansible
[2]: https://github.com/William-Yeh/docker-ansible#for-the-impatient
[3]: http://docs.ansible.com/ansible/latest/index.html

**Automatically updated when `williamyeh/ansible` changes**

# Example usage
Start Ansible shell using files in your current directory:  
```shell
docker run --rm -it -v $(pwd):/data -w='/data' colthreepv/ansible-shell
bash:/data # 
```

Start Ansible shell in current directory, using your current user SSH key:
```shell
docker run --rm -it -v $(pwd):/data -w='/data' -v ~/.ssh:/ssh colthreepv/ansible-shell \
-c 'mkdir ~/.ssh && cp /ssh/id_rsa ~/.ssh/; bash'
```

**Using Windows**  
Start Ansible shell in current directory, using your current user SSH key:
```shell
docker run --rm -it -v $(pwd):/data -w='/data' -v ~/.ssh:/ssh colthreepv/ansible-shell \
-c 'mkdir ~/.ssh && cp /ssh/id_rsa ~/.ssh/ && chmod 600 ~/.ssh/id_rsa; bash'
```
