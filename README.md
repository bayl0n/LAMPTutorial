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

Now something I had to figure out when learning the LAMP stack is how it all worked together. To put it simply, [TODO]
### Linux

Now when it comes to Linux, it doesn't really matter how you are able to use it as the LAMP stack pretty much works if you have a unix shell, whether it be from Ubuntu, Fedora, MacOS or even WSL (Windows Subsystem for Linux)!

For this tutorial I will be walking through how to install LAMP on Debian-based Linux distros as it is what I am most familiar with.

### Apache

Apache is our web server software. This is what is going to handle our handles requests such as HTTP and takes us to our webpage.

You can check if you have apache already insatlled on your system by typing 
```
which apache2
```
which should return a directory if it is installed. If not, you can install apache using the following command:
```
sudo apt-get install apache2
```

Now that it's installed, you can check the status of apache to see if it is running.
```
sudo service apache2 status
```
Where you will be returned the status of apache, but the main thing you are looking for is to see if apache is
```
**Active**: active running
```
If it isn't running you can simply type
```
sudo service apache2 start
```
And check the status again to see if apache is running.

Now that it's running, we can see a live demo of our apache web server but typing in ```localhost``` into any browser, which should return the *Apache2 Ubuntu Default Page*.
