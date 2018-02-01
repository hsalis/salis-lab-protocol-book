# ViennaRNA

### Installing

Download the source code to install. Step into the directory and run the following configure command line. It's important to use these flags 
```
cd ViennaRNA-2.4.2
./configure PYTHON2_DIR='/usr/local/lib/python2.7/dist-packages' PYTHON2_EXECDIR='/usr/local/lib/python2.7/dist-packages'
```

Read the last few lines of the configure script output. It should read:
```
##############################################
# Files will be installed in the following  ##
# directories:                              ##
##############################################

  Executables:        /usr/local/bin
  Libraries:          /usr/local/lib
  Header files:       /usr/local/include
  Extra Data:         /usr/local/share
  Man pages:          /usr/local/share/man
  Documentation:      /usr/local/share/doc/ViennaRNA
    (HTML):           /usr/local/share/doc/ViennaRNA/html
    (PDF):            /usr/local/share/doc/ViennaRNA
  Perl5 Interface:    Not to be installed
    (binaries):       
    (scripts):        
  Python2 Interface:  
    (binaries):       /usr/local/lib/python2.7/dist-packages
    (scripts):        /usr/local/lib/python2.7/dist-packages
  Python3 Interface:  Not to be installed
    (binaries):       
    (scripts): 
```

If it reads "Not to be installed" for the Python interfaces, it may be that you are mising a key file, python-config (certain Linux distros have this issue). It can be installed using:
```
sudo pip install python-config
```
If python-config is already installed, it will tell you.

Lastly to install ViennaRNA run the following two commands:
```
make
sudo make install
```