ansible-shell
=============
[![Docker Automated build](https://img.shields.io/docker/automated/colthreepv/ansible-shell.svg?style=for-the-badge&maxAge=3600)]()
[![Docker Pulls](https://img.shields.io/docker/pulls/colthreepv/ansible-shell.svg?style=for-the-badge&maxAge=600)]()  

This docker image let's you execute an [Ansible][3] control container with Bash  

[1]: https://github.com/William-Yeh/docker-ansible
[2]: https://github.com/William-Yeh/docker-ansible#for-the-impatient
[3]: http://docs.ansible.com/ansible/latest/index.html

**Automatically updated when `bash:5` changes**

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
