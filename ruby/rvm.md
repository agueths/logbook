# Ruby Version Manager

[rvm.io](https://rvm.io/)

# Ubuntu Install

## Pre-requisites

```term
sudo apt-get install software-properties-common
```

## 1. Add the PPA and install the package

```term
sudo apt-add-repository -y ppa:rael-gc/rvm
sudo apt-get update
sudo apt-get install rvm
```

Add your user to `rvm` group (`$USER` will automatically insert your username):

```term
sudo usermod -a -G rvm $USER
```    

## 2. Change your terminal window

Now, in order to always load rvm, change the Gnome Terminal to always perform a login.

At terminal window, click `Edit` > `Profile Preferences`, click on `Title and Command` tab and check `Run command as login shell`.

## 3. Reboot

A lot of changes were made (scripts that needs to be reloaded, you're now member of `rvm` group) and in order to properly get all them working, you need to reboot (in most cases a logout/login is enough, but in some Ubuntu derivatives or some terminal emulators, a shell login is not performed, so we advise to reboot).

## 4. Enable local gemsets

Now enable local gemsets.

```term
rvm user gemsets
```

## 5. Install a ruby

Now you're ready to install rubies.

```term
rvm install ruby
```

Or specify the version you want.

```term
rvm install 2.5.0
rvm --default use 2.5.0
```
