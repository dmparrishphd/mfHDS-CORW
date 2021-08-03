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

### Public Member Functions

`[[` returns one record (specified by arg 2) as a NCOL x NROW
matrix; element order is preserved.

`[` is a wrapper for `[[`. `[` returns the single record
corresponding with the step (arg 2), per(iod) (arg 3), and lay(er) (arg 4)
specified.

`dim` returns the dimensions of the grid (NCOL, NROW).

`image` **mutates** the current graphical device, displaying a
graphical representation of the record specified by arg 2.

`init` returns a new, initialized copy of the object. Arg 2
specifies the full path and filename of an HDS file.

`nrecords` returns the number of records in the HDS file.

`index` returns a matrix where row number = record number and
the named columns contain the corresponding PERiod and LAYer.

`transect` returns a matrix of values extracted for the layer
specified by Arg 2. The return has one column per PERiod and one
row per row of Arg 3. Arg 3 is an index matrix consistent with
matrix indexing of the `[` primitive.

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
