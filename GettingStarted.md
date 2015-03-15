For a brief overview of the setup and basic functionality of the Drupal Shift Scheduler, check out the [screencast for our 2.0 release](http://www.youtube.com/watch?v=x52i7lk2D1I).  This is also probably the best way to get to know the shift scheduler and whether it is the right tool for your organization.  The two screencasts for our 1.0 release ([1](http://www.youtube.com/watch?v=lhdtpUxhWc8), [2](http://www.youtube.com/watch?v=SpNn3d0lNEE)) provide very similar information and are available to watch online on YouTube, but you will notice a few small differences between the version used in those videos and the 2.0 release.

Covered in the screencast:
  * Installing the module
  * Defining slots
  * Adding and changing default shifts
  * Placing volunteers in shifts
  * Splitting shifts

For a full description of how to use the shift scheduler and all of its features, see the manual below.

Finally, if the shift scheduler does not meet your needs, please consider leaving feedback on the [Contact](Contact.md) page or filing a [feature request or bug report](http://drupal.org/project/issues/1075572).  You might also find [this](http://www.kamilslowikowski.com/2010/06/scheduling-solutions-for-volunteer-organizations/) list of alternative software useful.

**Table of Contents**


# Manual #

## Installation ##
The module is installed like any other Drupal module. (See the deprecated [screencast](http://www.youtube.com/watch?v=lhdtpUxhWc8) for the 1.0 release for details.)

It is highly recommended that you also install the [Multi-column checkboxes radios](http://drupal.org/project/multicolumncheckboxesradios) module, which will improve the display of some of the administrative pages.

Most of the time, the shift scheduler uses plain usernames to represent users in menus, schedules, etc. However, if you configure the Profile module on your installation (usually via Administer --> User management ---> Profiles) to have fields with the "Name" "profile\_first\_name" and "profile\_last\_name", the shift scheduler will use those in at least display to replace the bare usernames, which some find more aesthetically pleasing.


## General Terminology ##

For the purposes of this manual:

A **slot** refers to a particular role that needs to be filled when your organization is open or in service.  For example, if you're running an ambulance service, you might have the slots "Driver", "Paramedic", and "EMT-B" if those are the 3 people that staff the ambulance for every call.

A **shift** is a time range in which a slot needs to be filled.  For example, if I am going to drive the ambulance all night, I might say "I'm taking the 9pm to 9am _shift_ in the _Driver_ slot tonight."

A slot's **default shifts** are the shifts that people usually take in that slot when no special scheduling circumstances arise.  For example, Washington University's EST usually splits their 24-hour coverage of a single day into the 0900-1300, 1300-1700, 1700-2100, and 2100-0900 _default shifts_ for all three of their slots.

**Remember that all times are written in 24-hour military format, as in 0900, 0000, 1345.**

## Permissions ##

**Access Shift Schedule**: View the shift schedule and old shifts.

**Edit Shift Schedule**: Assign volunteers to shifts and split shifts.

**Add to Shift Schedule**: Add days to the shift schedule using the "Add Days" page (and the "Create Shifts for Event" page on Version 7-x-0-0 or greater)

**Administer Shift Scheduler**: Create and administer slots, access the "configure shift scheduler" menu.

## Slots ##

Slots can be created and administered by logging in as the webmaster and clicking the "Administer" link, followed by the "By Module" tab, and then finally clicking "Edit slots" under the "Shift Scheduler" heading.

To **add a slot**, simply fill in a slot name and click "Add Slot".


### Name ###
The slot's name is just that.  Changing a slot's name does not alter the slot in any other way.  In fact, while it is not recommended, you should be able to have two slots with the exact same name without causing any problems in the system.

### Status ###

Once a slot has been created, you can either "deactivate" or delete it.
  * When a slot is **active**
    * it is displayed in the main shift schedule
    * open shifts are added to it when days are added to the schedule
    * a record of all shifts taken it that slot is maintained in the database and can be reviewed at any time
  * When a slot is **deactivated**
    * it is not visible in the shift schedule
    * open shifts are never added to it
    * its history remains in the database undisturbed
  * When a slot is **deleted** it is almost as if the slot never existed
    * the slot is never displayed
    * open shifts cannot be added to it
    * all records of shifts taken in that slot are deleted from the database

### Slot type ###

Version 7-x-0-0 and higher only.

"Repeating" slots are the default. They are for shifts that need to be filled on a weekly or daily basis. For these slots, you will set "Default Shifts", which will be added to the schedule using the "Add Days" feature as described below.

"Event" slots only need to be filled occasionally during special events. Shifts for this slot will be created one at a time using the "Create Shifts for Events" feature, so the idea of a "default shift" doesn't apply to them.

### Eligible Roles ###

By default, the "authenticated user" role is eligible for a newly created slot.  This means that you can assign any user with an account on your Drupal website to a shift in that slot.

### Default Shifts ###

The default shifts for a slot are the shifts that will be filled it automatically when a day is "added" to the schedule.  (See corresponding section.)

To **create** a new default shift for a slot, click on the "edit default shifts" link next to that slot's name.  Then fill in the desired start time, end time, and days of the week using the two blank text boxes and the weekday checkboxes.  Then click "Update".

Please keep in mind that you cannot create default shifts that overlap.

To **delete** a default shift for a slot, simply delete it's start and end time and then click "Update".  You don't have to do anything with its weekdays.

## Adding Days ##

To **add a day** to the schedule means to create open shifts that correspond to that day.  For example, if I were to add Wednesday, May 26th to the schedule, the DSS will look at all of the default shifts for all of the slots that occur on Wednesday and create an "Open Shift" at each of those times on May 26th.  Once the shifts have been created, you can then go to the schedule and use the "change shift" page to place volunteers in each of the shifts.

To add a day to the schedule, click the "Add Days" link under the main "Shift Schedule" link (usually under your "Navigation" menu), select the date range that you would like to add (it includes the beginning and end days), and click "Create Days".

## Creating Event Shifts ##
(Version 7-x-0-0 and greater only)

Adding days only applies to slots of the "Repeating" slot type. "Event" shifts are created differently.

To create an "Event" shift, you go to the "Create Shifts for Events" menu item, which is found right underneath the "Add days" menu item.

From this page, you will select a date, a start time, and an end time. Then you will select from a list of "Slots" of the "Event" Slot Type which slots you need to be filled on that date and time. Open Shifts will be created on the specified date and time for the specified slots.

## Assigning Volunteers to Shifts ##

There are two ways that a volunteer can be assigned to a shift.

  1. Someone with the "edit shift schedule" permission can assign the member to the shift.
> 2. If "shift claiming" is enabled, the volunteer may claim the shift by him or herself.

### Editing the Shift Schedule ###

Users with the "edit shift schedule" permission will notice when they are looking at the shift schedule that many of the shifts they see appear as links.  In fact, this should be true for every shift that has not already occurred.  Each of these links brings the user to the **change shift** page corresponding to that shift.

The change shift page consists of 2 drop-down menus and a text box.  Each of the drop-down menus is populated with: 1) "Open Shift" 2) "Closed Shift" and 3) an alphabetical list of users that are eligible to take the shift.  (See "Eligible Roles".)  An **open shift** is a shift that needs to be assigned to a volunteer.  A **closed shift** is a shift that was created by the "Add days" page but actually shouldn't have anyone assigned to it.

To **open a shift, close a shift, or assign a volunteer to a shift**, simply select the appropriate option from the first drop-down menu, ignore the text box and the second drop-down, and click "Change Shift."  You will automatically be advanced to the "Change Shift" page for the next shift in the same slot.

Sometimes you would like to close only part of a shift, or it is impossible to find a volunteer who can take an entire shift.  In this case it is appropriate to **split the shift** between two or more volunteers.   To split a shift, simply fill in a time in the "Split Time" text box and click "Change Shift."  Be careful, though: you **cannot merge shifts**, so the schedule can start to look messy if there are many recklessly split shifts.    You can optionally fill in who you would like to take the first and second halves of the shift in the "Volunteer" and "Secondary Volunteer" drop-down menus.

### Claiming and Relinquishing Shifts ###

If **claiming shifts** is enabled, open shifts occurring in the future will appear as links to all logged-in users who are eligible to take them.  If the user clicks on the open shift link, that user will be assigned to that shift.  (If that user also has the "edit shift schedule" permission, she will instead be brought to the "Change Shift" page.)

If **relinquishing shifts** is enabled, users will see shifts that they are currently assigned to as links.  If the user clicks the link, he will be unasssigned and the shift will become an open shift.

## Viewing Old Shifts ##

Old shifts may be viewed either by date or by user.

To view old shifts by date, simply go to the shift schedule and select a date range to view from the top. Note that by default the shift schedule shows all shifts starting from yesterday through a few years from now.

To view old shifts by user, click on the "Old Shifts" link next to the under the main "Shift Schedule" link (usually under your "Navigation" menu), fill out the form, and click "Submit".