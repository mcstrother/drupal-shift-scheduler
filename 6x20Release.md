# DSS 6.x.2.0 Full Release is Out #

I am very pleased to announce the **full** release of the drupal shift scheduler 6.x.2.0!

The goal of this release is to focus on implemented "deal-breaker" features, which are features that are absolutely necessary for an organization to find the DSS useful.  [Click here](http://code.google.com/p/drupal-shift-scheduler/issues/list?can=1&q=milestone%3A6.x.2.0&colspec=ID+Type+Status+Priority+Milestone+Difficulty+Owner+Summary&cells=tiles)  for a complete list of the issues covered by this release.  A few highlights are:
  * default shifts can now be specified for different days of the week ([Issue17](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=17))
  * shifts that would normally need to be filled can be "closed" to indicate that no one needs to fill them ([Issue22](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=22))
  * admins can choose to allow people to sign themselves up for open shifts (shift "claiming", [Issue4](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=4)) or give up a shift they currently own (shift "relinquishing")
  * admins can choose to restrict which users can be placed in which slots using drupal roles ([Issue10](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=10), [Issue13](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=13))


Some changes that were made **since the 6.x.2.0-beta1 release**:
  * The module is now fully internationalized for all text except for dates ([Issue30](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=30), [Issue34](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=34), [Issue36](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=36))
  * The configuration page is now easily available with the config pages for all the other modules ([Issue29](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=29))
  * Fixed a bunch of benign (but annoying and scary) error messages ([Issue32](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=32))
  * Fixed shift claiming and relinquishing ([Issue38](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=38))
  * Slots are now displayed on the schedule in alphabetical order rather than in order of creation ([Issue37](https://code.google.com/p/drupal-shift-scheduler/issues/detail?id=37)) (If you're desperate to undo this, you can prefix the slot display names with numbers or manually undo the changes made to shift\_scheduler.module in r141da9d723.)
<a href='http://www.youtube.com/watch?feature=player_embedded&v=x52i7lk2D1I' target='_blank'><img src='http://img.youtube.com/vi/x52i7lk2D1I/0.jpg' width='425' height=344 /></a>

# Upgrade Instructions #

## From 6.x.2.0-beta1 ##
Just download the latest release, extract it, and replace the shift\_scheduler.module file you have currently running on your site with shift\_scheduler.module from the new release.


## From 6.x.1.0 ##

Just like any other drupal module:

  1. Download the latest version.
  1. Unzip it. (do not disable the old module)
  1. Delete the old module + folder.
  1. Replace old with new on server.
  1. Run update.php to update the database