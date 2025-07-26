# Proyecto InnovaSys

Automatización de la configuración de un servidor Ubuntu 24.04 con **Apache** y **Samba** usando **Ansible**.

Este proyecto crea:

- Un **servidor web interno (Intranet)** con Apache y una página de bienvenida personalizada.
- Un **servidor de archivos compartidos** con Samba, accesible solo por usuarios autorizados.

---

##  Requisitos

- Nodo de control con Ansible instalado (Linux Lite)
- Nodo gestionado con Ubuntu Server 24.04
- Conexión SSH entre el nodo de control y el servidor

---

## Como ejecutar el playbook
- Clonar el repositorio
git clone https://github.com/danifer866/ansible-innovasys.git
cd ansible-innovasys

## Edita el archivo inventario con los datos del servidor
[innovasys]
servidor-innovasys ansible_host=192.168.56.101 ansible_user=devops ansible_ssh_pass=Passw0rd ansible_become_pass=Passw0rd

## Ejecuta el playbook
ansible-playbook playbook.yml

## Accede desde el navegador
http://192.168.56.101

## En el gestor de archivos
smb://192.168.56.101/Proyectos
Usuario: devuser1
Contrase: Innova.2025

---

## Estructura

```bash
proyecto_innovasys/
├── ansible.cfg
├── inventario
├── playbook.yml
├── roles/
│   ├── apache/
│   │   ├── tasks/
│   │   ├── templates/
│   │   ├── vars/
│   │   └── handlers/
│   └── samba/
│       ├── tasks/
│       ├── vars/
│       └── handlers/

