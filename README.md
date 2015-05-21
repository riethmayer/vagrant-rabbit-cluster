# Vagrant Rabbit Cluster

This is a vagrant project containing 4 VMs with RabbitMQ cluster
and a Load Balancer.

## Requirements

This is not a standalone project and it should be used as a part
of [sevos/vagrant-devenv](https://github.com/sevos/vagrant-devenv)
installation.

It requires vagrant, virtualbox or VMWare and vagrant-dns plugin

## Installation

1. Go to your devenv installation directory
2. `git subtree add --prefix=projects/rabbit-test git@github.com:bonusboxme/vagrant-devenv-bonusbox.git master`
3. `vagrant up rabbit_{elb,1,2,3}`
