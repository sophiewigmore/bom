# Running Syft on a Maven app

Gets full information on all indirectly installed javen archive dependencies and Debian packages:
* name
* version
* url (source?)
* source version (for some, not all)
* location within layer
* licenses (for some, not all)
* CPEs

Notes:
* Only includes our indirectly installed java archive dependencies
* There are no entries for the Java/Maven/etc dependencies our buildpacks directly install
