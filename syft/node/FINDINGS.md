# Running Syft on a Node.JS app with no package manager

Gets full information on all *indirectly installed node modules* that come with Node:
* name
* version
* url (source?)
* source version (for some, not all)
* location within layer
* licenses (for some, not all)
* CPEs

Notes:
* Only includes our indirectly install node modules
* I don't see any entry for Node.JS itself, or Node version 14.17 that is installed
