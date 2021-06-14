# Running Tern on a Maven app

Gets full information on all indirectly installed java archive dependencies and Debian packages:
* name
* version
* source sha (for some, not all)
* location within layer
* licenses

Notes:

Notes:
* No CPEs
* Download URLs are present but empty for every entry
* This is file by file, rather than dependency by dependency. It is more fine
  grained than the Syft output.

* Includes image labels

* Only includes our indirectly installed java archive dependencies
* There are no top-level entries for the Java/Maven/etc dependencies our
  buildpacks directly install
