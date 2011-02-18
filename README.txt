// $Id$

Please see online documentation for more information.

== Installation Notes ==

It is highly recommended that you also install the Multi-column checkboxes radios module, which will improve the display of some of the administrative pages.

Most of the time, the shift scheduler uses plain usernames to represent users in menus, schedules, etc. However, if you configure the Profile module on your installation (usually via Administer --> User management ---> Profiles) to have fields with the "Name" "profile_first_name" and "profile_last_name", the shift scheduler will use those in at least display to replace the bare usernames, which some find more aesthetically pleasing.

**If you are upgrading from a previous version of Shift Scheduler that was hosted on Google Code** you should make sure that you have already upgraded to the most recent version availabe at http://code.google.com/p/drupal-shift-scheduler/downloads/list ("shift_scheduler-6-x-2-0.tar.gz"). You can then upgrade to this version simply by replacing all of the files in your installation folder with the files in this folder.
