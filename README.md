DeskCon
-------
Version 0.5

integrates your Android Device in the Desktop. Receive Notifications, Files
and Commands from your mobile Device on your Desktop PC. The Data is send over a
secure TLS Connection. The Connection is encrypted and authenticated with
self-signed Certificates (RSA-2048 PK).

Warning: This Project is still in development (beta) and may contain some Bugs or
         Security Holes. If you find any, please report them ^^


Information:
------------
    - Project Website https://github.com/fbarriga/deskcon-desktop
    - Google Play Store https://play.google.com/store/apps/details?id=cl.felipebarriga.deskcon


Requirements (Desktop Server):
------------------------------
    - Python >= 2.7 < 3.x
    - pyopenssl
    - GTK3

Requirements (Unity Client):
------------------------------
    - Python >= 2.7 < 3.x
    - from pip:
        - pip install -r requirements.txt
    - install binaries:
        - pygobject (GTK3) >= 3.22.0
        - AppIndicator3

Install:
--------
    - edito Makefile PREFIX is you don't want to install on /usr/local
    - sudo make install
    - open tcp ports 8082 and 8083 on your firewall
    - systemctl --user enable deskcon-server
    - (optional) make install-user-gnome-shell
      and activate the extension from the tweak-tool

Usage:
------
    - start the DeskCon Desktop Server:
        systemctl --user start deskcon-server
      or
        $PREFIX/lib/deskcon-desktop/deskcon.sh

    - start DeskCon Indicator:
        Launch DeskCon Indicator (from your desktop Accesories menu)
      or
        $PREFIX/bin/deskcon-indicator

    - (optional) change config File in ~/.deskcon
    - To pair with a new Device, start setup_device.sh or use the Gnome Extension or Unity Indicator
    - start DeskCon App on your Android Device
    - select Network > Desktop Hosts
    - click the + Button and enter the IP of your Desktop PC
    - check whether the Fingerprints match

Contacts:
---------
    - You may also DAVDroid, a CalDav Server (eg. Nextcloud), and GNOME Contacts
      to sync your Android contacts with GNOME 
      so that you may lookup contacts in the SMS Sending Interface
    
Todo:
-----
    - Translations
    - Mac/Windows support
    - Fingerprint validation via QR Code
    - Browser Extensions
    - Add option to automatically share clipboard
    - Pair client-server using resource discovery (broadcast would work fine)
    - Use external server to connect without local lan

Bugs:
-----
    - UI Design
