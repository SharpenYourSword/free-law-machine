Updates to the Free Law Machine are listed here by date.

2014-09-24:
 - A new version of the FLM was created at the request of a contributor. 
   This new version updates the code and dependencies and is considered v1.1.

2013-11-19:
 - This version of the FLM updates the code significantly, bringing in the 
   various improvements and dependencies that have grown out of the last
   few months. The v0.9 FLM was in great shape, and no new major features were
   needed. We're thus releasing this version as v1.0! 

2013-09-20:
 - The version of South that we are using had a regression that caused an
   issue in the free law VM. To fix it, we are going to install an older
   version of South and then fix the database manually. 

   Install the older South:

     sudo pip uninstall South
     sudo pip install South==0.7.5

   Fix the database:

     manage.py dbshell
     alter table "Document" alter column "court_id" type varchar(15);
     \q

   And you should be all set.
