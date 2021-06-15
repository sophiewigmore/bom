# Investigating BoM tools and formats

### [FIELDS.md](https://github.com/sophiewigmore/bom/blob/master/FIELDS.md)
Contains the BoM fields of interest and how we believe we can represent them in
CycloneDX and SPDX.


### Tools Investigations

#### Pack
* [Node.JS example](https://github.com/sophiewigmore/bom/blob/master/pack/node) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/no-package-manager)
* [NPM example](https://github.com/sophiewigmore/bom/blob/master/pack/npm) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/npm)
* [Yarn example](https://github.com/sophiewigmore/bom/blob/master/pack/yarn) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/yarn)
* [Go Mod example](https://github.com/sophiewigmore/bom/blob/master/pack/go-mod) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/go/mod)
* [Maven example](https://github.com/sophiewigmore/bom/blob/master/pack/maven) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/maven)


#### [Syft](https://github.com/anchore/syft)
* [Node.JS example from image](https://github.com/sophiewigmore/bom/blob/master/syft/from-image/node) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/no-package-manager)
* [NPM example from image](https://github.com/sophiewigmore/bom/blob/master/syft/from-image/npm) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/npm)
* [NPM example from image](https://github.com/sophiewigmore/bom/blob/master/syft/from-image/yarn) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/yarn)
* [Go Mod example from image](https://github.com/sophiewigmore/bom/blob/master/syft/from-image/go-mod) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/go/mod)
* [Maven example from image](https://github.com/sophiewigmore/bom/blob/master/syft/from-image/maven) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/maven)
--------------------------------
* [Node.JS example from source](https://github.com/sophiewigmore/bom/blob/master/syft/from-source/node) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/no-package-manager)
* [NPM example from source](https://github.com/sophiewigmore/bom/blob/master/syft/from-source/npm) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/npm)
* [NPM example from source](https://github.com/sophiewigmore/bom/blob/master/syft/from-source/yarn) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/yarn)
* [Go Mod example from source](https://github.com/sophiewigmore/bom/blob/master/syft/from-source/go-mod) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/go/mod)
* [Maven example from source](https://github.com/sophiewigmore/bom/blob/master/syft/from-source/maven) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/maven)


#### [Tern](https://github.com/tern-tools/tern)
* [Node.JS example](https://github.com/sophiewigmore/bom/blob/master/tern/node) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/no-package-manager)
* [NPM example](https://github.com/sophiewigmore/bom/blob/master/tern/npm) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/npm)
* [NPM example](https://github.com/sophiewigmore/bom/blob/master/tern/yarn) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/nodejs/yarn)
* [Go Mod example](https://github.com/sophiewigmore/bom/blob/master/tern/go-mod) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/go/mod)
* [Maven example](https://github.com/sophiewigmore/bom/blob/master/tern/maven) / [sample app used](https://github.com/paketo-buildpacks/samples/tree/main/maven)


#### Conclusions

CycloneDX (output of Syft examples) seems to fit our use case a bit better.
* Gets full information on all OS level and indirectly installed packages
  * CPEs, licenses, urls, shas, layer location, name, version
  * These are all fields we feel strongly about being first-class citizens
  * The SPDX output from Tern did not surface this metadata fully/or as clearly

* For all of our language modules (packages installed by go-mod and npm) can
  easily be retrieved with fully-fledged metadata
* It might be nice to integrate with this tooling rather than build out our own custom logic

* No information about the the actual dependencies we directly install (node,
  go, etc), but this is information that we can easily provide

* Does a better job of conveying the information we think is important
* The tooling ecosystem feels better fleshed out for the use cases we have (language module metadata collection)


#### To Do
* Offline environments?
* Conversion tooling
