![Logo](https://raw.githubusercontent.com/idealista/opengrok_role/master/logo.gif)

[![Build Status](https://travis-ci.com/idealista/opengrok_role.png)](https://travis-ci.com/idealista/opengrok_role)

# OpenGrok Ansible role

This Ansible role installs {OpenGrok in a Debian environment. The app is deployed to a Tomcat server and will expose the endpoint `yourtomcatip:8080/source/`.

- [Getting Started](#getting-started)
  - [Prerequisities](#prerequisities)
  - [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)
- [Built With](#built-with)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Contributing](#contributing)

## Getting Started

These instructions will get you a copy of the role for your Ansible playbook. Once launched, it will deploy [OpenGrok](https://opengrok.github.io/OpenGrok/) to a Tomcat server in a Debian system.

### Prerequisities

Ansible 5.2.0 version installed.
Inventory destination should be a Debian environment.
A Tomcat server needs to be installed in your host machine (you can install it using our [Tomcat role](https://github.com/idealista/tomcat-role)).

For testing purposes, [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver.

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

``` yml
- src: idealista.opengrok_role
  version: 1.0.0
  name: opengrok
```

Install the role with ansible-galaxy command:

```
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

``` yml
---
- hosts: someserver
  roles:
    - role: opengrok
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see the possible configuration properties.

## Testing

```
pipenv install -r test-requirements.txt
pipenv run molecule test
```

## Built With

![Ansible](https://img.shields.io/badge/ansible-5.2.0-green.svg)
![Molecule](https://img.shields.io/badge/molecule-3.5.2-green.svg)
![Goss](https://img.shields.io/badge/goss-0.36-green.svg)

## Versioning

For the versions available, see the [tags on this repository](https://github.com/idealista/opengrok_role/tags).

Additionaly you can see what changed in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors

* **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/opengrok_role/contributors) who participated in this project.

## License

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.
