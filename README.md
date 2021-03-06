<<<<<<< HEAD
CakePHP on OpenShift
====================

This git repository helps you get up and running quickly w/ a CakePHP installation
on OpenShift.  The backend database is MySQL and the database name is the
same as your application name (using $_ENV['OPENSHIFT_APP_NAME']).  You can call
your application by whatever name you want (the name of the database will always
match the application).


Running on OpenShift
----------------------------

Create an account at http://openshift.redhat.com/

Create a php-5.3 application (you can call your application whatever you want)

    rhc app create -a cake -t php-5.3

Add MySQL support to your application

    rhc cartridge add -a cake -c mysql-5.1

Add this upstream CakePHP repo

    cd cake
    git remote add upstream -m master git://github.com/openshift/cakephp-example.git
    git pull -s recursive -X theirs upstream master
    # note that the git pull above can be used later to pull updates to CakePHP
    
Then push the repo upstream

    git push

That's it, you can now checkout your application at (default admin account is admin/admin):

    http://cake-$yournamespace.rhcloud.com


NOTES:

GIT_ROOT/.openshift/action_hooks/deploy:
    This script is executed with every 'git push'.  Feel free to modify this script
    to learn how to use it to your advantage.  By default, this script will create
    the database tables that this example uses.

    If you need to modify the schema, you could create a file 
    GIT_ROOT/.openshift/action_hooks/alter.sql and then use
    GIT_ROOT/.openshift/action_hooks/deploy to execute that script (make sure to
    back up your application + database w/ 'rhc app snapshot save'first :) )

CakePHP Security:
    If you're doing more than just 'playing' be sure to edit app/config/core.php
    and modify Security.salt and Security.cipherSeed.
=======
# SpaceBukkit 1.2.1 - Web administration the awesome way!
A powerful yet simple web panel for administering your Bukkit Minecraft servers with ease.
http://spacebukkit.xereo.net

## Update
SpaceCP has been announced, a new, amazing administration panel that does everything except breakfast. Signup for beta on [http://spacecp.xereo.net](http://spacecp.xereo.net).

## Update
SpaceBukkit is a project developed aiming to bring an advanced and powerful web administration framework to Bukkit. What makes it unique is, on one hand, it's graphical user interface, and on the other hand some nifty features enlisted just below.

## Features
- General
    * Attractive Interface
    * Non lethal doses of awesomeness
    * Multiple Servers
    * Multi-user access with role setting
    * Theming Support
    * Per server - per user role settings
    * Console access
    * Chat access
- Dashboard
    * Pretty and quick statistics about your server
    * Activity feed - who did what, and when
    * Chat - talk with your players
- Players
    * Player management - kick, kill, feed, heal, ban, op and more!
    * Whitelist
    * Bans
- Plugins
    * Plugin management
    * Advanced Config editor
    * Installing and Deinstalling
    * Updating and disabling
    * Bukget integration (Plugin "app" store)
- Worlds
    * World management
    * Multiworld support
    * Backups
    * Chunkster
    * Dynmap
- Server
    * Craftbukkit one-click installing and updating
    * Server Properties saving
    * Schedules
    
## Credits
 * [Antariano](https://github.com/Antariano/) & [JamyDev](https://github.com/JamyDev/) - Web.
 * [NeatMonster](https://github.com/NeatMonster/) & [Drdanick](https://github.com/Drdanick/) - Java.

## Links
- Website: [http://spacebukkit.xereo.net](http://spacebukkit.xereo.net).
- Forums: [http://spacebukkit.xereo.net/forum](http://spacebukkit.xereo.net/forum).
- Wiki: [http://spacebukkit.xereo.net/wiki](http://spacebukkit.xereo.net/wiki).
 
## License
Copyright 2012 SpaceDev team (SpaceBukkit and SpaceCP development team)

SpaceBukkit Panel by SpaceBukkit is licensed under a 
Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License (THE LICENSE).
http://creativecommons.org/licenses/by-nc-sa/3.0/

Permissions beyond the scope of this license may be available at lucarager@gmail.com

CakePHP is licensed under
the MIT License

CakePHP(tm) : The Rapid Development PHP Framework (http://cakephp.org)
Copyright 2005-2011, Cake Software Foundation, Inc.

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the "Software"),
to deal in the Software without restriction, including without limitation
the rights to use, copy, modify, merge, publish, distribute, sublicense,
and/or sell copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.
>>>>>>> 5250672c74c6220f701eb979d4233b9ee8fab451
