# Net-Commander - Source Code Root Repository

Net-Commander IDE for IoT &amp; Automation

## General Information

This is the main source package of the Net-Commander IDE and it serves as repo for issues, wiki and general information only.

Since there are a few dozen other packages involved, please send pull requests through the appropriate repo.


**Attention:** This repo and document is being under construction and incomplete. There is no full source code for Net-Commander here.
We are currently porting lots of packages from SVN and Gitlab to here and into the npm package registry. Please come back in a few weeks.

## Index

<a href="#source" name="source">1. Overview</a>

<a href="#source" name="source">2. Source Code</a>

<a href="#links" name="links">3. Links</a>

<a href="#about" name="about">4. About</a>


<hr/>

## [1. Brief Overview - Source - Code & Packages](#overview)

<img src="https://raw.githubusercontent.com/net-commander/net-commander/Import/misc/overview_code.png"/><br/>

Notice: the diagram refers to the deployed version of the IDE. The source version differs. 

1. *Client - JS*: Dojo/AMD/Require-JS based application. Additional Dependencies: jQuery and a few Boostrap-3 plugins. This codebase is re-used by the Node-JS server app (see 9.) 

Internal Package Count: 7
External Minimum Packages: 5 
jQuery Plugin Count: 4


2. *PHP*: There is a self-written PHP framework with almost no dependencies in place. Its used by the IDE client over JSON-RPC-2.0 (with Dojo - SMD). This might get replaced by a Node-JS implementation since its only doing tiny things

3. *NGINX*: only needed when deployed. You can also just use your Apache or any other web-server

4. *Data-Files*: the IDE produces only data files, being consumed by the *device controller* (see 5.)

5. *Device - Controller*: A Node-JS application. In the deployed variant its compiled almost into all-in-one executable

6. *MQTT-Server*: Is driven by the Node-JS Mosca package and runs embedded in the main Node-JS application.

7. *WS-Server*: The web-socket server is primarily for the IDE or control-applications. Also MQTT commands go through this pipe.
 
8. *MQTT-Client*: Each external web client gets and internal and indirect MQTT connection. This connection is being used, or better said: abused to synchronize certain device states.

9. *Server-JS*: As mentioned, this part is using parts of the Client-Framework too. Only in some cases its using a server-side only implementation. That allows us to debug certain parts in the browser.  

10. *Mongo*: The MONGO server is rather optional, its used a storage adapter for Mosca and can be replaced for Redis or similar.



## [2. Source Code - Repositories](#source)

Since there different package managers in charge, the whole IDE is a composition of git sub modules.

### Documentation

The main repo of the doc-files: [https://github.com/gbaumgart/net-commander-documentation.git](https://github.com/gbaumgart/net-commander-documentation.git)

Documentation - Generator: [https://github.com/gbaumgart/daux.io.git](https://github.com/gbaumgart/daux.io.git). This is included as sub module above.

  
### Atom/Electron - Template

We are currently using a fork of the official electron-boiler template [here](https://github.com/gbaumgart/electron-boilerplate.git).

This repo holds all the Grunt tasks to create builds per platform. 

### PHP part for the IDE

Located here [https://gitlab.com/xamiro/xphp.git](https://gitlab.com/xamiro/xphp.git)

### Client part of the IDE

There are lots of packages involved. To have them all in place for development, we also created one main repository which uses git sub modules

Repo: [https://gitlab.com/xamiro/xjs.git](https://gitlab.com/xamiro/xjs.git)
 
Please check the Readme of this repo for more details

 
## [3. Main Links](#links)

- **Downloads** Please find all pre-build binaries on our [main page](http://net-commander.com/downloads)
- **Issues** You can post issues [here](https://github.com/gbaumgart/Net-Commander/issues)


## [4. About](#about)

This project is actively in development since the last 3.5 years and is based on shared interests between [MediaMerge, Inc.](http://mediamerge.com) and Pearls-Media-Publishing Ltd.

Media-Merge contacted us to develop further an abandoned project "Maqetta" from IBM. Since there was quit some overlap with our interests of developing App-Studios for the Mass, the project began instantly!

more tbc


