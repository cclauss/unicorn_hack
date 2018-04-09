# unicorn_hack
Installing unicorn into the __system__ Python 3 inside of a Python 3 VM fails.

Results: https://travis-ci.org/cclauss/unicorn_hack

# Why is sudo dependent on the Python version?
It is a mystery for me... We are pip installing into the System Python, not into the Travis CI Python.  However, my gut says that when "python" is not python2 then something in the unicorn build process generates a false message. Unicorn is Python 3 compatible but something in its build process is not.

# Why install into the system Python 3 instead of VM's Python 3?
We want to use __unicorn__ inside [GDB](https://www.gnu.org/software/gdb/) which leverages the system Python, not the VM's Python.

# Why not just use sudo for the pip install command?
Startup times at https://docs.travis-ci.com/user/reference/overview/#Virtualisation-Environment-vs-Operating-System
