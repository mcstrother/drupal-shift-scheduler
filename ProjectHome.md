Welcome to the documentation for the Drupal Shift Scheduler!

Code development and bug-tracking have moved to http://drupal.org/sandbox/mcstrother/1075572

"Shifts" are a common pattern in professional organizations.  This completely free and open source module can be plugged into any existing [Drupal](http://www.drupal.org) installation and supports maintaining an online schedule of shifts and employee work times.

drupal-shift-scheduler was originally designed for use by Washington University's Emergency Support Team, a collegiate emergency medical service, which needed a solution to maintaining a 3-person EMS crew 24 hours a day over 4 different shifts.  It is currently in use by this organization at http://est.wustl.edu/shift_scheduler

Module features:
  * Maintains a schedule of employees/volunteers
  * Easy access to historical shift information
  * Shifts on the schedule appear as links to users with appropriate permissions allowing users to edit a shift (change who is signed up for a shift, split shifts between two people, close a shift so no one needs to take it etc), "relinquish" a shift (set a shift that the user previously was signed up for to be "open"), or "claim" an open shift. Shift editing is optimized for certain repetitive tasks (e.g. copying physical sign-up sheets into the module)
  * The "slot" concept allows users/administrators with the appropriate permissions to define different positions that should be filled at any given time. (E.g. "driver", "EMT-B", and "Paramedic" for an ambulance corps or "manager", "register 1", "register 2" for a small store would all be different "slots".) Which users can be assigned to which slots can be defined with standard drupal "roles".
  * Users/administrators also define "default shifts" for each slot, which is in line with the way many organizations make their schedules and helps with speed of input and clarity and consistency of presentation. (See more detailed discussion in the GettingStarted page.)

If you are interested in using the drupal-shift-scheduler module, check out our GettingStarted page.

