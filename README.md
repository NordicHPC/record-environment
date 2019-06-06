# record-environment: get key information from users to assist debugging

`record-environment` is a wrapper that runs a command, but saves the
command line, output, relevant environment variables to a file.  This
file can be sent along with support requests, to hopefully get all
relevant information the first time.

[Sample user documentation](https://scicomp.aalto.fi/triton/help.html#getting-a-detailed-bug-report-with-triton-record-environment).



## Usage

Sample invocation (`-p` means to record extra Python-related variables):

```
record-environment -p python -V
```

Output:

```
Saving output to record-environment.out.txt
Python 3.6.8 :: Anaconda custom (64-bit)
```

Contents of record-environment.out.txt (partial, some data removed):
```
record-output running at Thu Jun  6 14:06:54 EEST 2019
<username>
<path-to>/record-environment
<hostname>

===== MODULES =====

Currently Loaded Modules:
  1) anaconda3/latest




===== QUOTA =====
Disk quotas for user <username>:
     Filesystem  blocks   quota   limit   grace   files   quota   limit   grace
home2-ib:/export/home/<username>
                 761808  10000000 11000000           34817       0       0        
~/.Xauthority size=709.



===== ENVIRONMENT (PARTIAL) =====
CPATH=/share/apps2/anaconda/anaconda3/latest/include
LD_LIBRARY_PATH=/share/apps2/anaconda/anaconda3/latest/lib
...


===== PYTHON path =====
/share/apps2/anaconda/anaconda3/latest/bin/python
/usr/bin/python2
/share/apps2/anaconda/anaconda3/latest/bin/python3
/share/apps2/anaconda/anaconda3/latest/bin/ipython
which: no ipython2 in (/share/apps2/anaconda/anaconda3/latest/bin:/usr/lib/qt-3.3/bin:/usr/lib64/ccache:/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/s
/share/apps2/anaconda/anaconda3/latest/bin/ipython3
/share/apps2/anaconda/anaconda3/latest/bin/pip
/share/apps2/anaconda/anaconda3/latest/bin/conda
‘/home/darstr1/.conda’

PYTHONPATH=/home/darstr1/pymod/:/m/cs/project/networks/darst/pymod/
_VIRTUALENVWRAPPER_API= mkvirtualenv rmvirtualenv lsvirtualenv showvirtualenv workon add2virtualenv cdsitepackages cdvirtualenv lssitepackages toggleg
VIRTUALENVWRAPPER_SCRIPT=/usr/bin/virtualenvwrapper.sh

sys.path:
['',
 '/home/darstr1/pymod',
 '/m/cs/project/networks/darst/pymod',
...


===== RUNNING COMMAND =====
===== python -V =====

Script started on Thu 06 Jun 2019 02:15:40 PM EEST
Python 3.6.8 :: Anaconda custom (64-bit)
```


## Installation and configuration

This is a single shell script... just copy to an executable path.

There is currently no configuration.


## Maintenance and development

Originally developed at Aalto Science-IT, but could use more
contributors.  This could be considered alpha to beta quality: it has
been used some, but not enough.