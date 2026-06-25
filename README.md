# Automatisierte Bereitstellung einer Jupyter-Plattform mit Vagrant, Ansible und Docker



## Projektbeschreibung



Im Rahmen des Moduls **Netzwerkbetriebssysteme** wurde eine automatisierte Bereitstellung einer Jupyter-Plattform umgesetzt.



Die Infrastruktur wird mit **Vagrant** und **VirtualBox** erstellt. Anschließend wird die virtuelle Maschine mittels **Ansible** konfiguriert. Docker wird automatisch installiert und ein Jupyter-Notebook-Container bereitgestellt.



---



## Verwendete Technologien



* Ubuntu 22.04 LTS

* Vagrant

* VirtualBox

* Ansible

* Docker

* Jupyter Notebook



---



## Architektur

<img width="1458" height="1034" alt="image" src="https://github.com/user-attachments/assets/913bf858-049c-4328-a54d-ff903cb8e362" />








## Virtuelle Maschine starten



```bash

vagrant up

```



Verbindung zur VM:



```bash

vagrant ssh

```

<img width="833" height="816" alt="image" src="https://github.com/user-attachments/assets/5310640a-ab86-4ef2-908e-3b3d466c6a31" />


---



## Ansible installieren



```bash

sudo apt update

sudo apt install ansible -y

```



---



## Docker Collection installieren



```bash

ansible-galaxy collection install community.docker

```



---



## Playbook ausführen



```bash

ansible-playbook -i ansible/inventory.ini ansible/playbook.yml

```



---



## Docker prüfen



```bash

sudo docker ps

```

<img width="1544" height="59" alt="image" src="https://github.com/user-attachments/assets/0e936afe-dbd3-4313-b888-ab0b20a12fcb" />

---



## Zugriff auf Jupyter



Im Browser:



```text

http://192.168.56.10:8888

```

<img width="1741" height="1069" alt="image" src="https://github.com/user-attachments/assets/66acb1cf-7437-46b8-808a-ea67c24c8aa2" />


Token:



```text

schule123

```

<img width="2554" height="1346" alt="image" src="https://github.com/user-attachments/assets/e82188e9-e49d-4381-8f01-ecdfd4a8297a" />


---



## Automatisierungsablauf



1\. Vagrant erstellt die Ubuntu-VM.

2\. Der Projektordner wird über `/vagrant` in die VM eingebunden.

3\. Ansible installiert Docker.

4\. Docker startet den Jupyter-Container.

5\. Jupyter ist über Port 8888 erreichbar.



---



## Ergebnis



Die Bereitstellung der Jupyter-Plattform erfolgt vollständig automatisiert. Durch die Kombination von Vagrant, Ansible und Docker kann die Umgebung jederzeit reproduzierbar erstellt werden.



