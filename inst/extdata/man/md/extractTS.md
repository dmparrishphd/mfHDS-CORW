extractTS
=========

Extract from a binary heads file the time series for specified cells.

Usage
-----

    extractTS <- source(paste0(pkg, "/inst/extdata/R/extractTS/", file)) [[ 1 ]]
    # WHERE `pkg` IS THE PATH TO THE PACKAGE DIRECTORY AND
    # `file` IS THE NAME OF A FILE IN THE inst/extdata/R/extractTS
    # PACKAGE SUBDIRECTORY.
    extractTS(hds, mi, echo = nullfile ())
    
| Argument | Description                  |
| -------: | :--------------------------- |
|      hds | An hds object                |
|       mi | An index matrix              |
|     echo | A file open for writing text |
    
Value
-----

A `matrix` with as many rows as the heads file has time steps and
as many columns as `mi` has rows. Each column contains the time
series associated with the cell specified by the corresponding
row of `mi`.

Details
-------

The `mi` argument must be a `matrix` of three columns.
Columns 1, 2, and 3 must specify
columns, rows, and layers, respectively,
of the MODFLOW grid.

The `echo` argument may be speficied as `stdout()`, `stderr()`, etc.

Examples
--------

    # SEE DOCUMENTATION ON proto FOR HOW TO OBTAIN Hds:
    HEADS <- extractTS(Hds,  matrix(1, ncol=3) , stdout())
    # ABOVE: EXTRACT TIME SERIES FOR COLUMN 1, ROW 1, LAYER 1.
