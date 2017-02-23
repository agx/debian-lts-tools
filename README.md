Helpers to ease debian-lts work

* *testpkg/Makefile*: add a local directory to apt's sources with a
  high priority

         mkdir lts-test
         wget --mirror https://people.debian.org/~user/wheezy-lts/
         make
         apt-get dist-upgrade
         <test manually>
         make clean
