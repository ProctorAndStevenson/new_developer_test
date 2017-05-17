# Contents

* [Introduction](#introduction)
* [Prerequisites](#prerequisites)
* [Getting Started](#getting-started)
* [The Test](#the-test)
* [Submitting the Test](#submitting)

<a name="introduction"></a>
# Introduction

This project consists of a basic Drupal website and database. The website forms part of the recruitment process for web developers at Proctor + Stevenson.

This project includes vagrant configuration files and ansible scripts to get it up and running quickly. You can of course use your local WAMP or MAMP installation instead if you wish.

<a name="prerequisites"></a>
# Prerequisites

If you want to use vagrant, you will need Virtual Box and Vagrant installed on your machine:

* [Virtual Box](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com/downloads.html)

You will also need [Ansible](http://docs.ansible.com/ansible/intro_installation.html).

You will need the following vagrant plugins:

[Vagrant Gatling Rsync](https://github.com/smerrill/vagrant-gatling-rsync)

This assumes you've got rsync installed. If you're running Windows, rsync installed with Cygwin or MinGW will be detected by Vagrant and works well. But you can also change the vagrant configuration to use any [sync mechanism you wish](https://www.vagrantup.com/docs/synced-folders/).

<a name="getting-started"></a>
# Getting Started

Once you've installed the necessary prerequisites, you should be able to navigate to the root directory and run

```
vagrant up
```

This will configure the box, and run the ansible scripts. The database for the project should be automatically installed, but if it is not, or you are not using vagrant, it is in the root of this directory:

```
/database.sql
```

The database user is "root" and the password is "root".

Once vagrant has finished creating the box, you'll see a bunch of information about it, this includes the IP address of the box, which should be:

```
10.10.10.89
```

You'll need to configure your hosts file to point the URL to that IP (or your local IP if you are not using vagrant).

```
10.10.10.89 proctorsdevtest.local
```

Then you should be able to access the site at:

[http://proctorsdevtest.local](http://proctorsdevtest.local)

To initiate the vagrant rsync, you can run (if it hasn't started automatically):

```
vagrant gatling-rsync-auto
```

This will sync any changes you make to your local files to the vagrant box.

<a name="the-test"></a>
# The Test

The instructions for the test are located in the project directory at

```
/instructions
```

There are instructions depending on whether you want to do the Drupal or Non-Drupal test. Which test you do is entirely up to you. **You don't have to do both.**


## If you are not familiar with Drupal

There are debugging functions, dpm() and dvm(). You will not see the output of these unless you are logged in. 

Access details to log in are in the instructions.

<a name="submitting"></a>
# Submitting the Test

We will need all the source code back to review your application. You can submit the via email attached as a zip file or download link and send to [recruitment@proctors.co.uk](mailto:recruitment@proctors.co.uk).

Ideally we should be able to download and unpack your files and then run `vagrant up` to see your code working. 

**Please also submit your CV, ensuring you list your name and the role you are applying for in the subject line.**
