# Manjaro/Arch
Esta es un playbook de Ansible que instala los paquetes iniciales para la configuración
de Lnux basado en arch.

## Pre-instalación

1. Actualizar e instalar Ansible + Git
```
sudo pacman -Syy
sudo pacman -S ansible git --noconfirm
```

2. Git clone el playbook.
```
git clone git@github.com:Caimapo/playbook.git
```

## Run

### Instalar todo
```
ansible-playbook playbook.yml --extra-vars="user_name=USERNAME user_email=EMAIL" --ask-become-pass
```

### Instalar todo modo debug
```
ansible-playbook -vvv playbook.yml --extra-vars="user_name=USERNAME user_email=EMAIL" --ask-become-pass
```
## Playbook Tags

Tags soportados:

| Tag       | Description                                                                                                      |
|-----------|------------------------------------------------------------------------------------------------------------------|
| base      | Install Linux util libraries, python-pip, xinput, terminator and zsh                                             |
| users     | Setup user accounts                                                                                              |
| printers  | Install printer drivers                                                                                          |
| browsers  | Install Chrome and chromedriver                                                                                  |
| dev-tools | Install jq, docker, docker-compose, nodejs, npm, jre8, jre10, maven, clojure, leiningen, sbt, scala, kubernetes, bluemix-cli and hub  |
| editors   | Install vim, atom, emacs, gimp and Intellij                                                                      |
| media     | Install Spotify and Peek (GIF Screen recorder)                                                                   |
| gnome/WM  | Configure the desktop environment                                                                                |
| aur       | Install Arch User Repository libraries                                                                           |


### Instalar solo un tag:
```
ansible-playbook playbook.yml --extra-vars="user_name=USERNAME user_email=EMAIL" --ask-become-pass --tags browsers
```