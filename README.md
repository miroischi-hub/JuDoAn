\# Automatisierte Bereitstellung einer Jupyter-Plattform mit Vagrant, Ansible und Docker



## Projektbeschreibung



Im Rahmen des Moduls \*\*Netzwerkbetriebssysteme\*\* wurde eine automatisierte Bereitstellung einer Jupyter-Plattform umgesetzt.



Die Infrastruktur wird mit \*\*Vagrant\*\* und \*\*VirtualBox\*\* erstellt. Anschließend wird die virtuelle Maschine mittels \*\*Ansible\*\* konfiguriert. Docker wird automatisch installiert und ein Jupyter-Notebook-Container bereitgestellt.



\---



\## Verwendete Technologien



\* Ubuntu 22.04 LTS

\* Vagrant

\* VirtualBox

\* Ansible

\* Docker

\* Jupyter Notebook



\---



\## Architektur



```text

Windows Host

│

├── VirtualBox

├── Vagrant

│

└── Ubuntu VM

&#x20;    │

&#x20;    ├── Ansible

&#x20;    ├── Docker

&#x20;    └── Jupyter Container

```



\---



\## Projektstruktur



```text

jupyter-ansible-vagrant/

│

├── Vagrantfile

├── ansible/

│   ├── inventory.ini

│   ├── playbook.yml

│   └── requirements.yml

│

└── README.md

```



\---



\## Virtuelle Maschine starten



```bash

vagrant up

```



Verbindung zur VM:



```bash

vagrant ssh

```



\---



\## Ansible installieren



```bash

sudo apt update

sudo apt install ansible -y

```



\---



\## Docker Collection installieren



```bash

ansible-galaxy collection install community.docker

```



\---



\## Playbook ausführen



```bash

ansible-playbook -i ansible/inventory.ini ansible/playbook.yml

```



\---



\## Docker prüfen



```bash

sudo docker ps

```



\---



\## Zugriff auf Jupyter



Im Browser:



```text

http://192.168.56.10:8888

```



Token:



```text

schule123

```



\---



\## Automatisierungsablauf



1\. Vagrant erstellt die Ubuntu-VM.

2\. Der Projektordner wird über `/vagrant` in die VM eingebunden.

3\. Ansible installiert Docker.

4\. Docker startet den Jupyter-Container.

5\. Jupyter ist über Port 8888 erreichbar.



\---



\## Ergebnis



Die Bereitstellung der Jupyter-Plattform erfolgt vollständig automatisiert. Durch die Kombination von Vagrant, Ansible und Docker kann die Umgebung jederzeit reproduzierbar erstellt werden.



