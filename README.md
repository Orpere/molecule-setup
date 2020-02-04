

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
- install pip 
  ```bash
  sudo easy_install pip 
  ```
- install ansible
  ```bash
  sudo pip install ansible
  ```
- upgrade ansible
  ```bash
  sudo pip install ansible --upgrade 
  ```
- install molecule
  ```bash
  pip install --user molecule
  ```
- test molecule
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
- use molecule 

