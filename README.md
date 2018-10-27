# Cookiecutter template for ansible playbooks

Template for ansible playbook with [molecule](https://molecule.readthedocs.io/en/latest/) testing

## Requirements

The template itself only needs python and cookicuter. Install it in a virtualenv if needed doing `pip install cookiecutter`

## What this template provides?

* Initialize a new git repo in the local machine
* Add [.yamllint](https://github.com/adrienverge/yamllint) config file (used by molecule)
* Add .pre-commit-config.yaml used by [pre-commit](http://pre-commit.com/)
* Add .gitignore with common files I don't want to track in git
* Add configuration for [Molecule](http://molecule.readthedocs.io) in the "molecule" folder
  * default molecule scenario uses Vagrant + centos7 (2GB ram)
  * second molecule scenario docker + centos/systemd image
  * molecule runs [testinfra](https://testinfra.readthedocs.io) in verbose mode
* And probably something else that I forget... :)

## Usage

### To initialize the playbook with cookiecuter
```
$ pip install cookiecutter
$ cookiecutter gh:pescobar/cookiecutter-ansible-playbook-molecule
```

### To initialize the playbook with molecule

```
$ molecule init template --url https://github.com/pescobar/cookiecutter-ansible-playbook-molecule
```

### To test the default scenario vagrant + centos7
```
$ molecule test
```

### To test the second scenario docker + centos/systemd image
```
$ molecule test -s docker
```
