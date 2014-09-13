# Running first-time

Run these commands in this order:

`git submodule update --init`

`vagrant up`

`vagrant ssh`

If it asks for a password give the password: `vagrant`

`cd /vagrant`

`bash run.sh`

# Running each time

`vagrant up`

`vagrant ssh`

`cd /vagrant/site/`

`gulp --require gulp-livescript`

`cd build`

`node server.js`

# Turning it off

`vagrant halt`

# Notes

- This is only the environment. I have let the site be a submodule.
	- It will just import the site and make it is own little git file. I'll also make sure that it pulls each submodule at some point when it runs.
	- I did this because I don't want people to get confused what the environment is there for. 
- You must have Virtualbox installed on your computer. 
	- https://www.virtualbox.org/
	- You don't need to download any specific OS or any environments. This will setup the rest for you!
- Also you need Vagrant: 
	- https://www.vagrantup.com/downloads.html
- Using older version of build-essential. Current does not work well with our version of chef. Git hash: 2bb0bfb
	- We can fix this by installing the chef-solo mod
		- `gem install chef`
		- Fixes this bug, but you can run into some complications that you should solve.
