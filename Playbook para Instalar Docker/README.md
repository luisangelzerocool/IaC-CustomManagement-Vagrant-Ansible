# Ansible

Playbook llamado “docker.yml” que instala Docker en el host_1

# Configuration the Host

In the machine with Ansible, to modificate the file `/etc/ansible/hosts` and enter the host where will install Docker for example:

```bash
[host_1]
192.168.1.8
```
## Conexión por SSH con el host

En la máquina central, ejecutamos: `ssh-keygen` 

Luego obtendremos el fichero publico .pub y privado en la ruta: ` ~/.ssh/` 

Copiamos la llave publica al host: `ssh-copy-id -i  ~/.ssh/id_rsa.pub root@192.168.1.8` 

Ejecutamos un ping desde Ansible a todos los host: `ansible all -m ping -u root` 

Luego obtenemos: 

```bash
192.168.1.8 | success >> {
	"changed": false,
	"ping": "pong"
}
```

# Execute Playbook

Execute the command: `ansible-playbook docker.yml` in the route where is docker.yml





