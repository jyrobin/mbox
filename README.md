Mbox
====

(This applies the patch given in Issue 34 to avoid the segmentation fault problem
for python3 thanking to Yu-Jie Lin).

Mbox is a lightweight *sandboxing* mechanism that any user can use
*without special privileges* in commodity operating systems. For more
details, see doc/NOTE.web or visit
[the website](http://pdos.csail.mit.edu/mbox/).

Getting started
===============

    $ cd src
    $ cp {.,}configsbox.h
    $ ./configure
    $ make

     - src/tests-sbox    : test codes
          /sbox.{c,h}    : system call hooks
          /mbox.c        : main

    $ ./mbox -h          : help
    $ ./mbox ls          : give it a shot
    $ ./testall.sh       : test all unit tests
    
    $ ./mbox -s ls       : run ls with seccomp/bpf (if supported)

Use cases
=========

    $ ./mbox -i -- wget google.com      : a simple use
    $ ./mbox -n -i -- wget google.com   : no network
