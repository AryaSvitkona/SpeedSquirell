# SpeedSquirell
Lightweight Mampstack (Apache, MariaDB, (multiple)PHP) with dnsmasq for local webapp development on OSX.
What does a squirell and this setup has in common? Speed,performance and a collection of the biggest nuts!
This repo provides you a "Step by Step" Guide and in the future a script which will do the whole work for you (WIP).

## Status quo
- You are going to write an web application, your first website or something else with PHP, HTML and other languages 
- You don't have a working development environment which is performant and usefull
- You love (at least like) working on OSX
- You're looking for something easy but configurable
- You won't spend money for MAMP Pro

## The Setup
If you follow the steps bellow, you will have a working environment in just a few minutes (depending on you) with:
- Apache 2.4 (Webserver)
- Maria DB 10.3 (like MySQL)
- PHP 7.2/7.3/7.4
- Dnsmasq (DNS Server)

## Step by Step guide
First, update your OSX to the latest version, open your terminal (found in /Applications/Utilities/) and grab a coffee!

1. Install XCode Tools
Run `xcode-select --install` to install a integrated development environment (IDE) developed by Apple.

2. Install Homebrew
Run `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"` to install the newest version of Homebrew.
Homebrew brings you the missing package manager for OSX (e.x that *apt-get install foobar* thing on Ubtunu)
After the installer ran trough, you can check the Version by run `brew --version`.
Check the website of Homebrew for more information: https://brew.sh/

2. Remove installed Apache webserver
The latest macOS 10.15 Catalina comes with Apache 2.4 pre-installed. Since that version has missing scripts and libraries, we will remove it and install the Homebrew version and then configure it to run on the standard port (80). Just run the following commands (Terminal will ask you for your "Login Passwort" since you run that command as sudo).
````
$ sudo apachectl stop
$ sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist 2>/dev/null
````
