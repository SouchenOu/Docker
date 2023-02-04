# Docker

I will talk about ---->
------------------


what is docker ?

what is container ?

what is virtualization ?

what is hypervisor ?


Difference between containerization vs virtualization ?

who is Docker for ?

What is docker image ?

What is a docker container ?

What is docker registry ?

What is docker client ?

What is a docker deomen ?

What is a docker namespace ?

---------------------------------------------------------------------------------------------------------------------------------------------

If we have been developping software for a While you have probably come across this situation ->where your application works on your development machine but doesnt somewhere else !! -->

Can you think of three reasons why this happens ??


The reasons is :
---------------

1: one or more files missing.

2: if the target machine running a different version of software that your application needs lets say your application needs node version 14
but the target machine is running node version 9.

3: and this can happen if the configuration settings like environment variables are different across these machines.

so Docker comes to the rescue -->

we can easly package up our application with everthing it needs and run it anywhere on any machine with docker, so if your application needs a given version of node and mongoDb all of these will be included in your applications package, now we can take this package and run it in any machine that runs Docker so if it works on your development machine is's definitely going to work on your test and production machines.

-->If someone joins your team they dont have to spend half a day or setting up a new machine to run your application they dont have to install and configure all these dependencies, they simpley tell docker to bring up your application and docker it self will automatically downloand and run these dependencies inside an isolated environement called a container.

and this is the beauty of docker this isolated environment allows multiple applications use different version of some software side by side
so one application may use node version 14 and another application may use node version 9, both these application can run side by side on the same machine without messing each other so this how docker allows us to consistently run an application on different machines.

There is one more benefit --> When we are done with this application and dont want to work on it anymore, we can remove this application and all its dependencies in one go, withut docker as we work on different projects our development machine gets cluttered with so many libraries and tools that are used by different applications and then after a while we dont know if we can remove one or more of this tools because we are always afraid that we are would mess up with some appication so with docker we dont have to worry about this because each application runs with its dependencies inside an isolated enviroment so we can safely remove an application with all its dependencies to clean up our machine is not that great!!

---------------------------------------------------------------------------------------------------------------------------------------------


What is Docker :
--------------

Docker is an open source platform that enables developers to build, deploy, run, update and manage containers—standardized, executable components that combine application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.


(Docker is a platform for building , running and shipping applications)


<img width="668" alt="Screen Shot 2023-02-02 at 11 00 25 AM" src="https://user-images.githubusercontent.com/87101785/216293831-46b228de-6f4c-4bfa-a7ba-f2b855ab0b6e.png">



An application running in a container is isolated from the rest of the system and from other containers

---> every application that will run in every container it will be isolate from others (other containers) it will be like that every application run in different operationg system  (but this is wrong  because we have one operating system at that time)

--> we can run a lot of containers in just one operator system by using docker.

(Multiple docker containers can be run on the single operating system simultaneously you can manage those containers with docker )

--> Docker is a container management service.


What is container :
-------------------


A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another.


What is virtualisation :
------------------------

OS virtualization is the use of software to allow a piece of hardware to run multiple operating system images at the same time.

(Having more than one operating system in one server..)


How does virtualisation work ?
------------------------------

Hypervisors take your physical resources (Processor, Ram, Hard disk) and divide them up so that virtual environement can use them .


virtualisation vs containerization :
-----------------------------------


<img width="891" alt="Screen Shot 2023-02-02 at 1 14 42 PM" src="https://user-images.githubusercontent.com/87101785/216323145-623a6ea9-f8d1-4b21-91a9-8d2078c6a009.png">


<img width="891" alt="Screen Shot 2023-02-02 at 1 24 10 PM" src="https://user-images.githubusercontent.com/87101785/216324331-a67c91c0-a061-4064-9ebb-352a00cdd8f2.png">

What is a docker image ?
-----------------------

An image is a read only template with instructions for creating a docker container. you may build, an image which is based on the ubuntu image and sqlServer.

Container :
-----------

container is an image that is running (When i install an application in docker it will be a container )

What is registry :
-----------------

A docker registry stores docker images. docker hub is a public registry that anyone can use 

What is client :
--------------

When you use commande such as docker run, the client send this command to docker 



<img width="891" alt="Screen Shot 2023-02-02 at 1 24 10 PM" src="https://user-images.githubusercontent.com/87101785/216330743-7b321b97-da15-4c04-b97d-5279df946e1e.png">

What is namespaces:
-------------------

Docker uses a technology called namespaces to provide the isolated workspace called the container.When you run a container docker creates a set of namespaces for that container.This namespace provide a layer of isolation.Each aspect of a container runs in a seperate namespace and its access is limited to that namespace.


Some ressources:
------------------

https://www.youtube.com/watch?v=DFyPl2cZM2g&list=PLX1bW_GeBRhDkTf_jbdvBbkHs2LCWVeXZ&index=2

Doker vs virtual machine:

https://www.youtube.com/watch?v=5GanJdbHlAA

Create docker-compose and run multiple containers
 
https://www.youtube.com/watch?v=MYV-7ao493k

The Layman's Guide to Linux: Daemons & Init Systems

https://www.youtube.com/watch?v=ydg9KZCCPE0

Full-course Docker:

https://www.youtube.com/watch?v=pTFZFxd4hOI


