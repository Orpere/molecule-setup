
# This repo show how to use and install [molecule](https://molecule.readthedocs.io/en/stable/index.html) on os x and [Ansible](https://www.ansible.com/)

![alt text](./molecule.png "molecule") ![alt text](./Logo-Red_Hat-Ansible-A-Reverse-SVG.svg "ansible")

- I use install zsh but is just m preference

  ```bash
  brew install zsh
  ```

  for the ones who like [ohmyzsh](https://github.com/ohmyzsh/ohmyzsh)

- install xcode

  ```bash
  xcode-select --install
  ```

- install [virtualenvrapper](https://swapps.com/blog/how-to-configure-virtualenvwrapper-with-python3-in-osx-mojave/)
  
- create your virtualenv

  ```bash
  mkvirtualenv molecule
  ```

  now for access the env you just have to

  ```bash
  ➜  ~ workon molecule
  (molecule) ➜  ~
  ```

- install molecule ansible and docker driver inside of the env

  ```bash
    pip3 install "molecule[lint,docker]"  
  ```

  ```bash
  molecule                                                                                                                      
  Usage: molecule [OPTIONS] COMMAND [ARGS]...

   _____     _             _
  |     |___| |___ ___ _ _| |___
  | | | | . | | -_|  _| | | | -_|
  |_|_|_|___|_|___|___|___|_|___|

  Molecule aids in the development and testing of Ansible roles.

  Enable autocomplete issue:

  eval "$(_MOLECULE_COMPLETE=source molecule)"
  
  ```

  ```bash
  molecule --version 
  ```

- use [molecule](https://www.jeffgeerling.com/blog/2018/testing-your-ansible-roles-molecule)
  
  ```bash
   molecule init role acme.test --driver-name docker    
   cd test

   molecule converge
    
   molecule destroy
  ```

- in case you need to test systemd **_this is not production grade is just to testing roles_** you can configure molecule.yml as our example

```yaml
---
dependency:
  name: galaxy
driver:
  name: docker
platforms:
  - name: centos8
    image: geerlingguy/docker-centos8-ansible:latest
    privileged: true
    command: "/lib/systemd/systemd"
    tmpfs:
      - /run
      - /tmp
    volumes:
      - /sys/fs/cgroup:/sys/fs/cgroup:ro
    capabilities:
      - SYS_ADMIN
    pre_build_image: true
  - name: ubuntu2004
    image: docker.io/geerlingguy/docker-ubuntu2004-ansible:latest
    privileged: true
    command: "/lib/systemd/systemd"
    tmpfs:
      - /run
      - /tmp
    volumes:
      - /sys/fs/cgroup:/sys/fs/cgroup:ro
    capabilities:
      - SYS_ADMIN
    pre_build_image: true
provisioner:
  name: ansible
verifier:
  name: ansible
lint: |
  yamllint .
  ansible-lint .
```
