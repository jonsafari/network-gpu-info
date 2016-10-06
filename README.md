# Network GPU Info

Display GPU utilization for all hosts in your network.


## Prerequisites
First setup SSH keys to all computers that you want GPU info about:
1. One time, from source computer:

       ssh-keygen -b 8192 -t rsa

2. For every remote computer, from your source computer:

       ssh-copy-id  yourusername@123.456.789.012


## Usage

    ./network-gpu-info [[user@]remote1 [[user@]remote2 [...]]]
    ./network-gpu-info hosts.txt

If your username is the same between your source and your target computers, you
don't need to prepend this to your remote host's address.  This info is passed
directly to the `ssh` command, so if it's valid when you use `ssh`, it will be
valid here.
The command-line argument can alternatively be a regular text file, consisting
of one entry per line.  For example:

    123.456.789.012
    user@remote1
    remote2
    another@10.0.0.5


## Todo
- Concurrent queries
- Pretty printing output
- Sorting output by utilization
- OpenCL support

Pull requests are welcome.
