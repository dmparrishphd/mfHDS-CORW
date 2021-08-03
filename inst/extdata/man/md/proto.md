proto
=====

Binary heads prototype object

Usage
-----

    
    Hds <- source(paste0(pkg, "/inst/extdata/R/proto/", file)) [[ 1 ]]
    # WHERE `pkg` IS THE PATH TO THE PACKAGE DIRECTORY AND
    # `file` IS THE NAME OF A FILE IN THE inst/extdata/R/proto
    # PACKAGE SUBDIRECTORY.

Value
-----

A `list` of several elements which, together, provide access to
MODFLOW binary heads output.

Details
-------

The intended use is to `source` the anonymous function call,
assign the return value to a name, and use the name to access
a binary heads file.

The full path to the file in the package subdirectory
"inst/extdata/R/proto" must be specified. The example usage
provides one such way of building the full path.

Examples
--------

    # SEE Usage Seciton FOR DESCRIPTION OF `pkg` AND `file`:
    Hds <- source(paste0(pkg, "/inst/extdata/R/proto/", file)) [[ 1 ]]
    file.hds <- stop("assign a valid heads file to file.hds")
    Hds <- Hds $ init ( Hds , file.hds )
    ls(Hds) # RETURN THE NAMES OF THE PUBLIC METHODS.
    Hds$dim(Hds)
    Hds$index(Hds)
    Hds$layers(Hds)
    Hds$nrecords(Hds)
    Hds$periods(Hds)
