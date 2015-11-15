# Development environment for Errbot plugins


## Requirements and recommendations

Download and install:

- [Vagrant](https://www.vagrantup.com/downloads.html)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

For keeping VirtualBox Guest Additions in sync, I recommend installing the
`vagrant-vbguest` plugin:

```
vagrant plugin install vagrant-vbguest
```

## Usage

Install any prerequisites listed in Requirements section.

Clone this project to your computer:

```
git clone https://github.com/alimac/errbot-dev.git
```

Build the `ubuntu/trusty64` box:

```
cd errbot-dev/
vagrant up
```

First run might take a while if it has to download `ubuntu/trusty64` box.
After it's done:

```
vagrant ssh
cd /vagrant
```

Here you should see a configuration file for Errbot (`config.py`) and a
directory called `err-data/`, where Err will store its plugin data and logs.
There is also `err-plugins/` directory, where you can put plugin directories
of the plugins you are developing.

You can update the configuration to use a particular backend, or run Errbot in
text mode:

```
errbot -T
```

If you run `errbot` from another directory, specify the path to
the configuration file:

```
errbot -T -c /vagrant/config.py
```

## Errbot configuration

This project ships with very minimal configuration setup for Errbot.
These are the variables that it sets:

```
BOT_DATA_DIR = '/vagrant/err-data'
BOT_EXTRA_PLUGIN_DIR = '/vagrant/err-plugins'
BOT_LOG_FILE = '/vagrant/err-data/err.log'
BOT_LOG_LEVEL = logging.DEBUG
```
