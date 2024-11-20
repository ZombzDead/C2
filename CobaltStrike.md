
# CobaltStrike

Cobalt Strike is a platform for adversary simulations and red team operations. The product is designed to execute targeted attacks and emulate the post-exploitation actions of advanced threat actors. This section describes the attack process supported by Cobalt Strike’s feature set. The rest of this manual discusses these features in detail.

Reference: https://hstechdocs.helpsystems.com/manuals/cobaltstrike/current/userguide/content/cobalt_cobalt-strike_userguide.pdf

### Initial Install
    $ download.cobalstrike.com/download
    $ cd Downloads 
    $ tar zxvf cobaltstrike-dist.tgz
    $ mv cobaltstrike /opt/tools/cobaltstrike
    $ cd /opt/tools/cobaltstrike
    $ ./update

Reference: https://hstechdocs.helpsystems.com/manuals/cobaltstrike/current/userguide/content/topics/install_installing.htm

### Usage

Activate Teamserver

    $ cd opt/tools/cobaltstrike 
    $ sudo ./teamserver <Host_IP> <password>
Leave Terminal Open 

Open new Terminal to start Cobaltstrike 

    $ sudo ./cobaltstrike
    $ cd /opt/tools/cobaltstrike
Server Connection window will pop up: Input Host, Port, username, and teamserver password 
Select "Connect" 

### Create a Listener

You will be required to create a listener for your compromised machines to connect to.

      Select Cobalt Strike > Listeners (on top left corner of GUI)
      At the bottom of the page Select "Add" (to create a Listener)
      Once all information has been put in, Select "Save"
In the Input Window, input a domain name that points to your team server. 

### Delivering Payload
    - On the top bar, Select "Attacks" > Web Drive-by > Scripted Web Delivery (This will provide us a Powershell one-liner to run on the victim host)
    - Payload will be generated, Copy/Paste the URL into Notepad, then select "OK" to close the window.
    - Copy/Paste Payload onto the Victim's host into Powershell. 
    - On the Linux system, in Cobalt Strike, go to the "Events Log". It should show you that a beacon has been established with the Victim's host. 

### Interacting with Victim Host
    - Right click on the Victim Host, go to the username and select "Interact"
  
### Elevate Attacks
    Access > Elevate

### VNC Attack
    Explore > Desktop (VNC)

### Dump Hashes
    Access > Dump Hashes

### Pivoting
    Interact > net computers 
    List computers > (right click and select "Jump")

Use net [pid] [arch] [command] [arguments] to inject the network and host enumeration tool into the specified process. 
Use net [command] [arguments] (without [pid] and [arch] arguments) to spawn a temporary process and inject the network and host enumeration tool into it. 
An exception is the net domain command which is implemented as a BOF.net domain. 

    computers - lists hosts in a domain (groups)
    dclist - lists domain controllers. (populates the targets model)
    domain - display domain for this host
    domain_controllers - lists DCs in a domain (groups)
    domain_trusts - lists domain trusts
    group - lists groups and users in groups
    localgroup - lists local groups and users in local groups. (great during lateral movement when you have to find who is a local admin on another system).
    logons - lists users logged onto a host
    sessions - lists sessions on a host
    share - lists shares on a host
    user - lists users and user information
    time - show time for a host
    view - lists hosts in a domain (browser service). (populates the targets model)

## Community Kit

Community Kit is a central repository of extensions written by the user community to extend the capabilities of Cobalt Strike. The Cobalt Strike team acts as the curator and provides this kit to showcase this fantastic work. 
Some scripts have Binaries that need to be removed prior to use! 

### Initial Install

    $ sudo git clone https://github.com/Cobalt-Strike/community_kit.git
    $ cd community_kit
    $ sudo ./community_kit_downloader.sh  

### To load Scripts:
    Cobalt Strike > Script Manager> Load - Navigate to scripts
    $ /opt/tools/community_kit/community_kit 

Reference: 
- https://github.com/Cobalt-Strike/community_kit
- https://cobalt-strike.github.io/community_kit/
