# AppController
Control each App within each Cloud

AppController is a beginning OpenSource Application able to scale up and down your business App within any cloud provider.

# Continuous Integration
![alt tag](https://travis-ci.org/bzhtux/AppController.svg)

# Design
![alt tag](https://raw.githubusercontent.com/bzhtux/bzhtux.github.io/master/statics/AC_Design_Modules.png)

*Modules and main workflow schema*

# Goals
1st goal is to provide an agnostic cloud provider and elastic solution for all applications.
This App is python and C/c++ written application. Python is used for connectors and C/C++ is used for intelligence.
C/C++ is able to scale, so this is the reason why we choose python and C/C++.

AppController should be agnostic with monitoring systems such as cloud providers.

# Core
AppController is build on top of 4 main modules :
 * Collector
 * Scheduler
 * Core/intellignece
 * Deploy
Each module has a simple goal with several methods.

## Collector
Collector module's goal is to collect health datas from Customer App. Health datas is gathered by group (for a 3tier WebApp : Cacheflow, AppFlow and DataFlow)
Collector module has to collect health values from each group that compose Customer Application, not only hosts health !
Those values are returned to Core module that decide wich action to provide.

## Scheduler
Scheduler module provides a scheduled plan for Customer App. Scheduler module acts Linux crontab. Scheduler module also provides a random check for all Customer App group.

## Core
Core module provides intelligence for AppController App.
Core module looks for tresholds and decide with a algorythm wich action to deploy :

* scale up : extend Customer infrastructure
* scale down : scale down Customer App resources

# Community
You want to involve yourself in an opensource project dealing with Cloud, fell free to contact me :
bzhtux @ gmail.com
