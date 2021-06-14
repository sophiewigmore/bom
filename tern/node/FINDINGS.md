# Running Tern on a Node.JS app with no package manager

Gets every file within the node_modules directory and reports:
* name
* version
* source sha (for some, not all)
* location within layer
* licenses

Notes:
* No CPEs
* Download URLs are present but empty for every entry
* This is file by file, rather than dependency by dependency. It is more fine
  grained than the Syft output.

* Includes image labels

* Only includes our indirectly install node modules

* Includes an entry for node, but has no version (line 257415)
