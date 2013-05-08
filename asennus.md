#Installing TMC server to ubuntu 12 LTS
## Expectations
* Ubuntu server installed
* ruby 1.9.3-p327 installed and available on every user.

## Install some dependencies
Mainly for tmc-server Ruby on Rails app, java, X if on headless setup
`apt-get install git zip unzip imagemagick openjdk-6-jdk openjdk-6-jre openjdk-6-jre-headless ant maven xorg build-essential git curl zlib1g-dev autoconf`

Install apache2, optional if only for development
`apt-get install apache2`

For development install screen:
`apt-get install screen`

##Configuting TMC server

###Cloning TMC-Server
Clone tmc-server and update git submodules
Submodules may reguire having ssh access to these repositories, or doing it manually...
`git clone https://github.com/testmycode/tmc-server.git && cd tmc-server && git submodule update --init --recursive`

###Installing gems and dependenciens
 `sudo apt-get install libxslt-dev libxml2-dev` for nokogiri.  
`sudo apt-get install libqt4-dev libqt4-core g++` for capybara-webkit  
`sudo apt-get install libsqlite3-dev ` for Rails  
`sudo apt-get install postgresql libpq-dev` for Postgresql  
`gem install rails` You might need to install rails  

#### Bundle install
`gem install bundler && bundle install`  

###Configuring config/site.yml
Based on config/site.defaults.yml
Just read that file. No need for (major) changes. You may leave the file as it is for development

###Configuring DB
Configure postgresql9.* and add it to tmc-server/config/database.yml

You may need to config postgres to allow md5 auth instead of peer
### Setup database
`rake db:reset` for development db
`env RAILS_ENV=production rake db:reset` for prodution db
`env RAILS_ENV=test rake db:reset` for prodution db


#Installing TMC-sandbox
`cd ext/tmc-sandbox/`  
Install some dependencies for tmc-sandbox: 
`apt-get install squashfs-tools multistrap build-essential e2fsprogs e2tools`  

If you're on a Debian derivative, you may need to install Debian's archive key:  
`curl -L http://ftp-master.debian.org/archive-key-6.0.asc | sudo apt-key add -`  

## Make tmc-sandbox
`sudo make`  
`cd web/`  
`bundle install`  
`rake ext`  
`rvmsudo rake init:install`  


#Finishing tmc-servers installation
At tmc-server/  `bundle install`  
`rake compile` (later `rake recompile`)  
`sudo apt-get install realpath`  
`rvmsudo rake comet:init:install`  if RAILS_ENV==PRODUCTION  
Change comet urls in config/site.yml  if RAILS_ENV==PRODUCTION and base_url_for_remote_sanboxes port 3000 -> port 80 if RAILS_ENV==PRODUCTION  
`rake comet:config:update` if RAILS_ENV==PRODUCTION  
`rvmsudo rake reprocessor:init:install`  if RAILS_ENV==PRODUCTION  

`apt-get install libapache2-mod-xsendfile`  if RAILS_ENV==PRODUCTION and using apache  

##C-project support
For now, tmc server, like tmc-sandbox, requires installation of `check`, `gcc` (build-essential) and `pkg-config`. You can install all of those using apt-get
`apt-get install check gcc pkg-config build-essential`

#Setup
## Production
`sudo /etc/init.d/tmc-comet start`  
`sudo /etc/init.d/tmc-submission-reprocessor start`  
`sudo /etc/init.d/tmc-sandbox start`  
ruby on rails compliant web server.
# Dev
`.script/dev-env/`
