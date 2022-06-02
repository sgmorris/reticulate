
# Introduction ------------------------------------------------------------

# Exploring the "reticulate" package - getting python code to run
# on the R console

# stephen.morris@dpi.nsw.gov.au
# 2022-06-02

# Package load ------------------------------------------------------------
library(reticulate)
library(lubridate)

# Install miniconda (one time)
# install_miniconda()

# check what we are working with
py_config()

# and you can specify which python to use via
# use_python() or set the environment variable RETICULATE_PYTHON
# discover what's available
py_discover_config()


# Python module install/load ------------------------------------------------------

# there is a default environment "r-reticulate" created
# here: C:\Users\morriss\AppData\Local\r-miniconda\envs for
# local module loads
use_condaenv("r-reticulate")

# install modules - note pip=TRUE to search the python repositories
# 
py_install(envname="r-reticulate", packages="datetime", pip=TRUE)
py_install(envname="r-reticulate", packages="pandas", pip=TRUE)
py_install(envname="r-reticulate", packages="numpy", pip=TRUE)

# now import the modules to the R environment
datetime <- import("datetime")
pandas <- import("pandas")
numpy <- import("numpy")


# Python function calls ---------------------------------------------------

# now can access the functions in the modules via "$"
# eg date function converts arguments to a date class
# note force arguments to integer class from the R end
testdate <- datetime$date(as.integer(2001), as.integer(10), as.integer(12))
testdate
str(testdate)
testdate-1

# or send date object from R to the datetime utilities
mydate <- seq(ymd("2000-01-01"), ymd("2010-01-01"), by="2 months")
datetime$date$strftime(mydate[1], format="%A %d. %B %Y")


# running python scripts --------------------------------------------------
# this script defines a function "add" with 2 arguments x, y 
source_python("adding.py")

dd <- add(x=10, y=3)




