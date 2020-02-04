

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
    pip install ansible molecule docker 
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
  molecule, version 2.22
  ```
- use [molecule](https://www.jeffgeerling.com/blog/2018/testing-your-ansible-roles-molecule)
  
  ```bash
   molecule init role -r test -d docker
   cd test

   molecule converge
    
   molecule destroy
  ```