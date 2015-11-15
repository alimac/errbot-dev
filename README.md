# Development environment for Errbot plugins


## Requirements and recommendations

- Vagrant
- VirtualBox

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

You can update the configuration to use a particular backed, or run Errbot in
text mode:

```
errbot -T
```

If you run `errbot` from another directory, specify the path to
the configuration file:

```
errbot -T -c /vagrant/config.py
```
