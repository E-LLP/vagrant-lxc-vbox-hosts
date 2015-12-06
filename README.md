# vagrant-lxc ready VirtualBox machines

Basically a set of Vagrant VirtualBox machines ready for [vagrant-lxc](https://github.com/fgrehm/vagrant-lxc)
usage, serving as "live documentation" on how to set up hosts for using the plugin.

## :warning: Deprecated

[I've stepped down as a maintainer of the plugin](https://github.com/fgrehm/vagrant-lxc/issues/375) and I'm no longer maintaining this repo. Feel free to use it as a starting point for your own boxes and if you need any help with that just LMK! :beers: 

## Usage

```
$ git clone https://github.com/fgrehm/vagrant-lxc-vbox-hosts.git
$ cd vagrant-lxc-vbox-hosts
$ vagrant up BOX_NAME
$ vagrant reload BOX_NAME
```

## Available boxes

| BOX_NAME | Distro |
| -------- | ------ |
| precise | Ubuntu 12.04 64 bits |
| quantal | Ubuntu 12.10 64 bits |
| raring  | Ubuntu 13.04 64 bits |
| saucy   | Ubuntu 13.10 64 bits |
| trusty  | Ubuntu 14.04 64 bits |
| wheezy  | Debian 7.0 64 bits |
