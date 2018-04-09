# unicorn_hack
Installing unicorn inside a Python 3 VM fails.

Results: https://travis-ci.org/cclauss/unicorn_hack

# Why is sudo dependent on the Python version?

It is a mystery for me... We are pip installing into the System Python, not into the Travis CI Python.  However, my gut says that when "python" is not python2 then something in the unicorn build process generates a false message. Unicorn is Python 3 compatible but something in its build process is not.
