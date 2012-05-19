# libspatialite
This builds sqlite3 with spatial features (ie. positioning, coordinates, poloygons, etc.) for iOS using an Xcode static library project.

Include in it are the GEOS and PROJ projects which builds into their own individual libaries albeit really huge in size 43mb and 1.7mb respectively.

By default, the project just builds the libspatialite library without GEOS and PROJ support by firstly not linking them and defining the `OMIT_GEOS` and `OMIT_PROJ` definitions.

Should these libraries need to be built and included, just link the libspatialite target with the GEOS and PROJ libraries and remove the C Flags of `OMIT_GEOS` and `OMIT_PROJ`, clean and rebuild.

## Currently
5.7mb when built with spatialit (-GEOS -PROJ)e and the sqlite3 (+RTree +FTS3) amalgamation.

## Caveat
If you want things like distance between points, it is inevitable that you ahve to include the GEOS and PROJ packages which does bring SQLite to 43mb. [Distance Functions](http://www.gaia-gis.it/gaia-sins/spatialite-sql-3.0.0.html#p13)
