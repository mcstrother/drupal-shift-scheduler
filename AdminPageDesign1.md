# Status #

This design has been implemented, and is a part of the drupal-shift-scheduler-6.x-1-0 release.

# Goals #

Provide a web UI to modify the following features:
  * Number of slots
  * Name of slots (e.g. Medic 1, Medic 2, Medic 3)
  * Standard shifts that are filled in once days are added (preferably, we should be able to specify different default shifts for each slot, but have them default to all being the same)

UI to modify the following features would be nice, but is secondary to the features above:
  * The order of appearance on the duty schedule display

Things that are not targeted for this enhancement, but might be nice one day:
  * Different default shifts for different days
  * Restrictions on which users can be placed into which slots.


## Number of Slots ##
Want to be able to Add a slot, delete a slot, and "deactivate" a slot.

Deleting a slot: deletes the slot and every shift ever taken in that slot.  Make the database as if that slot never existed.

Deactivate a slot:
  * do not display the slot in the duty schedule
  * do not add shifts to the slot when adding days
  * otherwise leave the slot unchanged.  Continue to show the slot in old duty displays

# Design #

Ease of implementation is the primary criteria here.

Copy as much as possible from the curren Roles UI:
  * Columns: Names, operations
  * Rows: 1 for each slot.  Name, Edit Slot (link), Edit Default Shifts (link)

Edit Slot should link to a page that looks exactly like the Roles's "Edit Role" page--i.e. it should have a text box for entering the slot's name and two buttons "Save Slot" and "Delete Slot."

Edit Default Shifts should link to a page with a table of the existing default shifts.  Each should have a start time and end time labeled in adjacent columns.  Each should have a button to the right of it labeled "Delete".  At the bottom of the table, there should be a place to enter a start time and an end time (military time, no colons) and with a button to the right labeled "Add Shift".

# Implementation #

Tutorial for drupal module configuration page is [here](http://drupal.org/node/206761).

## Phase 1: Editing Slot Names ##
Easiest since it only affects a display name and not any functionality or database tables.

## Phase 2: Editing Default Shifts ##

Second easiest, since it only affects Adding Days.

## Phase 3: Deactivating Slots ##

## Phase 4: Adding Slots ##

## Phase 5: Deleting Slots ##

The easiest, but the least useful.

