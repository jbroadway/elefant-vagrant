# Virtual Machines for Elefant Development

This project provides scripts and workflow for developing LAMP-based
web applications, with the additional option of installing the latest
Elefant CMS code into a new site.

**Status:** Used for personal/work development, still being fleshed out
for wider general use. Bug reports, suggestions and improvements are
most welcome.

## Requirements

Tested on Mac OS X, and requires the following tools:

* [Berkshelf](http://berkshelf.com/)
* [Chef-solo](http://gettingstartedwithchef.com/)
* [Vagrant](http://www.vagrantup.com/)
* [VirtualBox](https://www.virtualbox.org/)

## Getting started

Once you've installed the above tools, clone and initialize your
setup like this:

	git clone https://github.com/jbroadway/elefant-vagrant ~/projects
	cd ~/projects
	berks install

This will create a `~/projects` folder, under which all of your web
projects will be run.

Now to create your first project, use:

	sudo ./new-project testsite elefant

This command does several things:

1. Adds a new `www.testsite.dev` alias to `/etc/hosts`
2. Creates a Vagrant project under `~/projects/testsite`
3. Installs Elefant into this folder and sets the necessary permissions
4. Starts the virtual machine (`vagrant up`)

After the script completes successfully, you should be able to browse
to `http://www.testsite.dev/` and be taken to the Elefant installer.

Your source files live in `~/projects/testsite/www` on the host machine,
which is mapped to `/var/www/elefant` in the virtual machine.