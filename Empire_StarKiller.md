# Empire

Empire is a post-exploitation and adversary emulation framework that is used to aid Red Teams and Penetration Testers. The Empire server is written in Python 3 and is modular to allow operator flexibility. Empire comes built-in with a client that can be used remotely to access the server. There is also a GUI available for remotely accessing the Empire server, Starkiller.

Reference: https://github.com/BC-SECURITY/Empire

### Initial Install
    $ cd /opt/tools
    $ git clone --recursive https://github.com/BC-SECURITY/Empire.git
    $ cd Empire
    $ ./setup/checkout-latest-tag.sh
    $ ./ps-empire install -y

### Update Empire
    $ sudo apt install powershell-empire 
### Usage

    $ sudo powershell-empire --username empireadmin --password password123

### Clean up Empire Database
    $ Empire/data/reset.sh



# Starkiller

Starkiller is a Frontend for Powershell Empire. It is a web application written in VueJS.

Reference: https://github.com/BC-SECURITY/Starkiller

### Initial Install
    $ curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
    $ echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
    $ sudo apt update && sudo apt install yarn 
    
    $ apt install Node.js 
    
    $ yarn --VERSION
    $ yarn install
    $ yarn electron:serve
    $ yarn electron:build:lin
    $ cd dist_electron/
    $ cd tools/Starkiller

### Usage

    $ sudo powershell-empire server

Starkiller should automatically populate with the Empire Listener.
Launches Starkiller from the terminal window. Doesn't need to have an empire listener already running but does need the empire server running in its own terminal window 


