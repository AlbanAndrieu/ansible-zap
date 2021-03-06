## [![Nabla](https://debops.org/images/debops-small.png)](https://github.com/AlbanAndrieu) roles/alban_andrieu_zap

This file was generated by Ansigenome. Do not edit this file directly but instead have a look at the files in the ./meta/ directory. 

[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![Travis CI](https://img.shields.io/travis/AlbanAndrieu/ansible-zap.svg?style=flat)](https://travis-ci.org/AlbanAndrieu/ansible-zap)
[![Branch](http://img.shields.io/github/tag/AlbanAndrieu/ansible-zap.svg?style=flat-square)](https://github.com/AlbanAndrieu/ansible-zap/tree/master)
[![Donate](https://img.shields.io/gratipay/AlbanAndrieu.svg?style=flat)](https://www.gratipay.com/~AlbanAndrieu)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-alban.andrieu.zap-660198.svg?style=flat)](https://galaxy.ansible.com/alban.andrieu/zap)
[![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)
[![Docker Hub](https://dockerbuildbadges.quelltext.eu/status.svg?organization=nabla&repository=ansible-zap)](https://hub.docker.com/r/nabla/ansible-zap/)


This ``Simple`` role allows you to install [Zap](https://code.google.com/p/zaproxy/) zaproxy service
which can be used to perform penetration testing.

### Installation

This role requires at least Ansible `v2.3.0.0`. To install it, run:

Using `ansible-galaxy`:
```shell
$ ansible-galaxy install alban.andrieu.zap
```

Using `arm` ([Ansible Role Manager](https://github.com/mirskytech/ansible-role-manager/)):
```shell
$ arm install alban.andrieu.zap
```

Using `git`:
```shell
$ git clone https://github.com/AlbanAndrieu/ansible-zap.git
```

### Documentation

More information about `alban.andrieu.zap` can be found in the
TODO [official alban.andrieu.zap documentation](https://docs.debops.org/en/latest/ansible/roles/ansible-zap/docs/).


### Role variables

List of default variables available in the inventory:

```YAML
zap_enabled: yes                       # Enable module

#zap_listen_ip: "127.0.0.1"
#zap_port: "8090"

## Where to install zap and Unix user/group
#user: "{{ lookup('env','USER') }}"
zap_owner: "zap"
#zap_owner: "{{ user }}"
zap_group: "{{ zap_owner }}"
zap_shell: "/bin/false" #/bin/bash
zap_base_dir: "/usr/local/zap"
#home: "{{ lookup('env','HOME') }}"
#zap_owner_home: "{{ home }}"
zap_owner_home: "{{ zap_base_dir }}"
zap_link_base_dir: "/opt"
zap_dir_tmp: "/tmp" # or override with "{{ tempdir.stdout }} in order to have be sure to download the file"
zap_user_state: present
#zap_pkg_state: present

## Most likely you dont need to edit
#todo zap_service_enabled   : 'yes'
zap_major: "2"
zap_minor: "4.3"
zap_build: ""
zap_version: "{{zap_major}}.{{zap_minor}}"
zap_name: "zap-{{zap_version}}"
zap_archive_extracted: "ZAP_{{zap_version}}{{zap_build}}"
zap_archive: "{{zap_archive_extracted}}_Linux.tar.gz"
zap_url: "https://github.com/zaproxy/zaproxy/releases/download/{{zap_version}}/{{zap_archive}}"
#zap_url: "http://sourceforge.net/projects/zaproxy/files/{{zap_version}}/{{zap_archive}}/download"
#zap_url: "http://downloads.sourceforge.net/project/zaproxy/{{zap_version}}/{{zap_archive}}?r=&ts=1411599584&use_mirror=skylink"
zap_home_dir: "{{zap_base_dir}}/{{zap_name}}"

docker_files_generated_directory: "./"
docker_files_enable: no
docker_volume_directory: "{{ zap_base_dir }}"
docker_working_directory: "/home/vagrant"
docker_image_name: "nabla/ansible-zap"
```


### Detailed usage guide

This ansible script has been created to work with [zaproxy maven plugin](https://github.com/AlbanAndrieu/zap-maven-plugin).
This plugin is tested using the following project [bodgeit-maven](https://github.com/AlbanAndrieu/bodgeit-maven).
For Jenkins I recommend using [Zapper+Plugin](https://wiki.jenkins-ci.org/display/JENKINS/Zapper+Plugin) with or without this ansible playbook
I would suggest using the following role in order to get zap tool for manual testing [Ansible owasp wte - Web Testing Environment](https://github.com/AlbanAndrieu/ansible-owasp-wte)

### Testing
```shell
$ ansible-galaxy install alban.andrieu.zap
$ vagrant up
```

### Contributing

The [issue tracker](https://github.com/AlbanAndrieu/ansible-zap/issues) is the preferred channel for bug reports, features requests and submitting pull requests.

For pull requests, editor preferences are available in the [editor config](.editorconfig) for easy use in common text editors. Read more and download plugins at <http://editorconfig.org>.

In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

### Authors and license

`roles/alban_andrieu_zap` role was written by:

- [Alban Andrieu](fr.linkedin.com/in/nabla/) | [e-mail](mailto:alban.andrieu@free.fr) | [Twitter](https://twitter.com/AlbanAndrieu) | [GitHub](https://github.com/AlbanAndrieu)

License
-------

- License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)

### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/AlbanAndrieu/ansible-zap/issues)!

***

This role is part of the [Nabla](https://github.com/AlbanAndrieu) project.
README generated by [Ansigenome](https://github.com/nickjj/ansigenome/).

***

Alban Andrieu

[linkedin](fr.linkedin.com/in/nabla/)