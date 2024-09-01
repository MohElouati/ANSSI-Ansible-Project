# Projet Ansible

## Description

Ce projet vise à sécuriser les systèmes sous AlmaLinux 9 en automatisant leur configuration à l'aide d'Ansible, conformément aux recommandations de l'Agence nationale de la sécurité des systèmes d'information (ANSSI). La sécurité informatique étant une priorité essentielle, ce guide et ces scripts Ansible sont conçus pour simplifier la mise en œuvre de configurations sécurisées, tout en renforçant la protection contre les menaces actuelles. Les principales tâches automatisées crée une infrastructure à la fois sécurisée et facile à gérer.

## Structure du Projet

- **`ansible/`**: Contient les playbooks et les rôles Ansible utilisés pour les différentes tâches de configuration et de sécurisation.
- **`Repartitions taches.md`**: Document de répartition des tâches entre les membres de l'équipe, listant les responsabilités spécifiques et les tâches à accomplir.
- **`Status.md`**: Indique le statut des différentes tâches de configuration avec une légende simple pour comprendre l'état de chaque tâche.

Il faut mettre le réseau en Bridge.
Il faut activer le EFI dans les paramètres système

### réaliser une connexion SSH ?

1. Mise à jour globale : 
	
   sudo dnf update -y
   sudo dnf upgrade -y

   # Install the OpenSSH server
   sudo dnf install -y openssh-server

   # Enable and start the SSH service
   sudo systemctl enable sshd
   sudo systemctl start sshd
   # Install essential tools
   sudo dnf install -y git wget curl vim

   # Install EPEL repository if not already installed
   sudo dnf install -y epel-release

   # Install Ansible
   sudo dnf install -y ansible

   # Install httpd
   sudo dnf install httpd

2. [Alma Linux] Générer une paire de clés SSH :
   
   ```bash
   ssh-keygen -t rsa -b ""
   ```

3. [Alma Linux] Autoriser la connexion via Root :
   
   ```bash
   nano /etc/ssh/sshd_config
   ```
   ```bash
   Modifier : "PermitRootLogin Yes"
   ```
   
4. [Ansible] Configurer SSH :
   
   ```bash
   ssh-keygen
   ```
   ```bash
   ssh-copy-id user@vm-ip-address
   ```


## Installation

1. Cloner le dépôt :
   
   ```bash
   git clone https://github.com/MohElouati/ANSSI-Ansible-Project
   cd ansible
   ```

2. Configurer l'hôte distant :
   
   ```bash
   nano hosts.ini
   ```
3. Configurer Run_Playbook.yml : 

   Changer le user.
    ```bash
      nano Run_Playbook.yml
    ```

4. Lancer le playbook :
   
   ```bash
   ansible-playbook -i hosts.ini Run_Playbook.yml --ask-become-pass 
	become : 12345678
   ```

---