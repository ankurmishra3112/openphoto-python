Tests for the Open Photo API / Python Library
=======================
#### OpenPhoto, a photo service for the masses

----------------------------------------
<a name="requirements"></a>
### Requirements
A computer, Python 2.7 and an empty OpenPhoto instance.

---------------------------------------
<a name="setup"></a>
### Setting up 

Create a tests/tokens.py file containing the following:

    # tests/tokens.py
    consumer_key = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    consumer_secret = "xxxxxxxxxx"
    token = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    token_secret = "xxxxxxxxxx"
    host = "your_hostname"

Make sure this is an empty test server, **not a production OpenPhoto server!!!**

---------------------------------------
<a name="running"></a>
### Running the tests

    cd /path/to/openphoto-python
    python -m unittest discover -c

The "-c" lets you stop the tests gracefully with \[CTRL\]-c.

The easiest way to run a subset of the tests is with nose:

    cd /path/to/openphoto-python
    nosetests -v -s tests/test_albums.py:TestAlbums.test_view

---------------------------------------
<a name="test_details"></a>
### Test Details

These tests are intended to verify the Python library. They don't provide comprehensive testing of the OpenPhoto API, there are PHP unit tests for that.

Each test class is run as follows:

**SetUpClass:**

Check that the server is empty

**SetUp:**

Ensure there are:

 * Three test photos
 * A single test tag applied to each
 * A single album containing all three photos

**TearDownClass:**

Remove all photos, tags and albums