Updates
=======
Updates to the Free Law VM are occasionally announced on the dev list, but are 
always posted at:
 - https://www.courtlistener.com/tools/free-law-machine/updates.md
 
Sample Data
===========
Sample data can be used for testing or other purposes and can be found in 
various sizes at:
 - https://www.courtlistener.com/tools/sample-data/
 
Be sure to check out the readme for instructions on how to install it, and note
that if this data is very old, it likely will not match the current schema of 
your system.


The Free Law Machine
====================
This virtual machine was created for developers of software for the Free
Law Project. We have made an effort to pre-configure this machine with 
sane defaults for developers. Changes to this effect range from the 
mundane to the insane. Those changes are listed herein. If you wish to 
change the default Virtual Machine used by developers, please get in touch, as
we are happy to update our defaults to make everyone's experience better. You 
can also make requests or file issues here:

 - https://github.com/freelawproject/free-law-machine/issues

To personalize this machine after you receive it, there are a couple steps YOU
should take:
    
 1. Disable this note from popping up every time you start the system by going
    into "Startup Applications..." in the upper right corner of your screen. 
    It's on the desktop if you should wish to read it again.
 
Note as you are looking around that a handful of things are already running:
 - The CourtListener database is set up and running (postgres)
 - The Solr search engine is set up and running with multiple cores in place.
 - Tabs are pinned for you in Firefox, so you can see:
    - The solr admin interface
    - Your local version of CourtListener
    - Our task tracker in Trello
    - The Free Law XPath tester
 - In addition, Intellij is set up with two projects. These are at:
     /home/freelaw/Programming/intellij/courtlistener
     /home/freelaw/Programming/intellij/juriscraper
   When you open these, you'll find that they have run configurations available
   to you:
    - Juriscraper is set up to run tests
    - CourtListener is set up to run 'manage.py runserver', the Django testing 
      server


Host Requirements
-----------------
The host machine, if Linux, needs to be running at least a kernel newer than 
version 3.5. You can check if this is the case by running `uname -a`. Failure
to have this will almost certainly result in an unstable working environment.


Password
--------
The only user on this machine is "freelaw". The password for this user is 
"freelaw". Some passwords for the CourtListener installation are "password", 
but in general, things are set to "freelaw". This would never fly in production,
but we can happily develop like this without issue.


CourtListener Configuration
---------------------------
The CourtListener platform has been installed on this system and configured
within the default IDE, Intellij. The installation has been documented 
[elsewhere][1], however, in general, this involved:
 + Dependancy installation (via apt-get and pip)
 + CourtListener and Juriscraper are installed and configured as Intellij
   projects (~/Programming/Intellij/).
 + Postgres is installed, configured for CourtListener, and tested.
 + Solr is installed, configured for CourtListener, and tested.
 + Apache, Tesseract, and RabbitMQ are NOT installed.


Configuration Changes
---------------------
 + The Ubuntu sidebar has been pruned and updated with better programs
 + The file browser has been configured to have a Delete action and to have a 
   better default view.
 + Screen lock and passwords are off.
 + Ubuntu telemetry is off.
 + VMWare Tools are installed.
 + Sound is muted; all alert sounds are disabled.
 + Backups are off.
 + Clock is set to 24-hour time.
 + The .bashrc and .vimrc files have been upgraded.


Global Software Changes
-----------------------
 + We have installed and configured the following programs:
    + Intellij -- A closed-source IDE, which we have licensed
        + Added Python support via the Python plugin
        + Enabled Dark mode
        + Enabled line numbers
        + Telemetry is disabled
        + The CourtListener database is configured for the Django and root users
    + Geany -- For text editing
    + Meld -- For merging changes from upstream 
    + Chrome -- For alternative to Firefox, if needed
    + Firefox has been configured with the following extensions:
    	- Chatzilla -- for IRC
    	- Firebug
    	- HttpFox
    	- JSONovich
    	- Modify Headers
    	- Tamper Data
    	- User Agent Switcher -- Configured with Juriscraper
    	- Web Developer
	+ Sun Java -- required by Intellij, suggested by Solr.
	+ Kiki -- For regex work
	+ Xacobeo -- For XPath work (though we generally recommend the Free Law 
	  XPath tester at http://xpath.courtlistener.com)
	+ htop, vim

Again, we can't thank you enough for your contributions to the Free Law Project.
Every bit of your efforts helps to ease the legal burden in America.

Now, get to work! 
	
[1]: https://github.com/freelawproject/courtlistener/wiki/Installing-CourtListener-on-Ubuntu-Linux
