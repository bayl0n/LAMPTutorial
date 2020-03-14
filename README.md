# LAMPTutorial
A basic tutorial on how to install LAMP on Ubuntu and Debian-based Linux distros

## What is LAMP?
The LAMP stack is an acronym for a set of open-source software that can be used to create websites and web applications.

It stands for:

* **L**inux - The operating system
* **A**pache - The web server
* **M**ySQL - The database
* **P**HP - The programming language

## How to set it up

Now something I had to figure out when learning the LAMP stack is how it all worked together. To put it simply, the LAMP stack is meant to be used over a virtual machine using a hosting service. This means that your website will be hosted on a virtual machine somewhere with Linux installed on it along with Apache, MySQL and PHP, which you will be accessing remotely from your local machine.

However, for this tutorial, I will be teaching you how to get LAMP installed locally on your computer without using a VM from  a cloud-service.

### Linux

Now when it comes to Linux, it doesn't really matter how you are able to use it as the LAMP stack pretty much works if you have a unix shell, whether it be from Ubuntu, Fedora, MacOS or even WSL (Windows Subsystem for Linux)!

There are many Linux-distros to choose from such as Ubuntu, Fedora, openSUSE, Arch, etc - however, whichever OS you use doesn't really matter and is totally personal preference

But for now, in this tutorial I will be walking through how to install LAMP on Debian-based Linux distros as it is what I am most familiar with.

### Apache

Apache is our web server software. This is what is going to handle our handles requests such as HTTP and takes us to our webpage.

#### Checking if Apache is installed

You can check if you have apache already installed on your system by typing 
```
which apache2
```
which should return a directory if it is installed.

#### Updating your packages

If you haven't alreaady, make sure your packages are up to date by running the following command:
```
sudo apt update
```

#### Installing Apache

If not, you can install apache using the following command:
```
sudo apt-get install apache2
```

#### Making sure that Apache is running 

Now that it's installed, you can check the status of apache to see if it is running.
```
sudo service apache2 status
```
Where you will be returned the status of apache, but the main thing you are looking for is to see if apache is
```
Active: active running
```
If it isn't running you can simply type
```
sudo service apache2 start
```
And check the status again to see if apache is running.

#### Checking out our Apache Web Server

Now that it's running, we can see a live demo of our apache web server but typing in ```localhost``` into any browser, which should return the *Apache2 Ubuntu Default Page* if everything has been done correctly. If you don't see this make sure that apache is running by rereading the **Making sure that Apache is running** section.

#### Giving permissions

when you create your web sever using Apache, your user won't be able to edit files, as you will have read-only permissions. To fix this, you need to give your user permission to do so using the following command:
```
sudo chown -R USER /var/www/html/
```
where ```USER``` is the name of the user you want to give access to.

### MySQL

MySQL is an open-source relational database management system.

#### Checking that MySQL is installed

You can check if you have installed MySQL by simply typing ```mysql```

#### Installing MySQL

To install MySQL, use the following command
```
sudo apt install mysql-server
```
which should install MySQL
