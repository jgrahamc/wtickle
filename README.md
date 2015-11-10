# wtickle

Small program to run requests against a web server and look for
problems. Has very compact output with optional detailed log
file. Reads a list of URLs (one per line) from stdin and then randomly
hits them.

# Options

* `-par`: The number of parallel requests to perform (defaults to 1)

* `-duration`: The length of time to run the test for (0 means forever and
 is the default)

* `-header`: optional extra HTTP header to add to each request

* `-log`: optional name of file to write detailed log information to.

# Example

    $ cat urls
    http://www.example.com/
    http://www.example.com/somepage
    http://www.example.com/nested/page
    http://www.example.com/index.php
    http://www.example.com/login

    $ ./wtickle -log=log.txt -duration=10s -par=100 < urls

# Output symbols

* `.` 200 OK with no error

* `e` some internal error in the program

* `3` 3xx error from the server

* `4` 4xx error from the server

* `5` 5xx error from the server




