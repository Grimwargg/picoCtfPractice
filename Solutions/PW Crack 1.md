convertme.py

Description
Can you crack the password to get the flag? Download the password checker here (https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted flag (https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.

Solution

//download the files
grimwarg-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.py
--2025-02-03 16:45:54--  https://artifacts.picoctf.net/c/12/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                                           100%[=================================================================================================================================================================>]     876  --.-KB/s    in 0s      

2025-02-03 16:45:54 (28.8 MB/s) - 'level1.py' saved [876/876]

grimwarg-picoctf@webshell:~$ ls
README.txt  level1.py
grimwarg-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
--2025-02-03 16:46:13--  https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                                                 100%[=================================================================================================================================================================>]      30  --.-KB/s    in 0s      

2025-02-03 16:46:13 (9.18 MB/s) - 'level1.flag.txt.enc' saved [30/30]

//read some help about how to run a python script
grimwarg-picoctf@webshell:~$ python3 --help
usage: python3 [option] ... [-c cmd | -m mod | file | -] [arg] ...
Options and arguments (and corresponding environment variables):
-b     : issue warnings about str(bytes_instance), str(bytearray_instance)
         and comparing bytes/bytearray with str. (-bb: issue errors)
-B     : don't write .pyc files on import; also PYTHONDONTWRITEBYTECODE=x
-c cmd : program passed in as string (terminates option list)
-d     : turn on parser debugging output (for experts only, only works on
         debug builds); also PYTHONDEBUG=x
-E     : ignore PYTHON* environment variables (such as PYTHONPATH)
-h     : print this help message and exit (also -? or --help)
-i     : inspect interactively after running script; forces a prompt even
         if stdin does not appear to be a terminal; also PYTHONINSPECT=x
-I     : isolate Python from the user's environment (implies -E and -s)
-m mod : run library module as a script (terminates option list)
-O     : remove assert and __debug__-dependent statements; add .opt-1 before
         .pyc extension; also PYTHONOPTIMIZE=x
-OO    : do -O changes and also discard docstrings; add .opt-2 before
         .pyc extension
-q     : don't print version and copyright messages on interactive startup
-s     : don't add user site directory to sys.path; also PYTHONNOUSERSITE
-S     : don't imply 'import site' on initialization
-u     : force the stdout and stderr streams to be unbuffered;
         this option has no effect on stdin; also PYTHONUNBUFFERED=x
-v     : verbose (trace import statements); also PYTHONVERBOSE=x
         can be supplied multiple times to increase verbosity
-V     : print the Python version number and exit (also --version)
         when given twice, print more information about the build
-W arg : warning control; arg is action:message:category:module:lineno
         also PYTHONWARNINGS=arg
-x     : skip first line of source, allowing use of non-Unix forms of #!cmd
-X opt : set implementation-specific option. The following options are available:
         -X faulthandler: enable faulthandler
         -X showrefcount: output the total reference count and number of used
             memory blocks when the program finishes or after each statement in the
             interactive interpreter. This only works on debug builds
         -X tracemalloc: start tracing Python memory allocations using the
             tracemalloc module. By default, only the most recent frame is stored in a
             traceback of a trace. Use -X tracemalloc=NFRAME to start tracing with a
             traceback limit of NFRAME frames
         -X importtime: show how long each import takes. It shows module name,
             cumulative time (including nested imports) and self time (excluding
             nested imports). Note that its output may be broken in multi-threaded
             application. Typical usage is python3 -X importtime -c 'import asyncio'
         -X dev: enable CPython's "development mode", introducing additional runtime
             checks which are too expensive to be enabled by default. Effect of the
             developer mode:
                * Add default warning filter, as -W default
                * Install debug hooks on memory allocators: see the PyMem_SetupDebugHooks()
                  C function
                * Enable the faulthandler module to dump the Python traceback on a crash
                * Enable asyncio debug mode
                * Set the dev_mode attribute of sys.flags to True
                * io.IOBase destructor logs close() exceptions
         -X utf8: enable UTF-8 mode for operating system interfaces, overriding the default
             locale-aware mode. -X utf8=0 explicitly disables UTF-8 mode (even when it would
             otherwise activate automatically)
         -X pycache_prefix=PATH: enable writing .pyc files to a parallel tree rooted at the
             given directory instead of to the code tree
         -X warn_default_encoding: enable opt-in EncodingWarning for 'encoding=None'
         -X int_max_str_digits=number: limit the size of int<->str conversions.
             This helps avoid denial of service attacks when parsing untrusted data.
             The default is sys.int_info.default_max_str_digits.  0 disables.

--check-hash-based-pycs always|default|never:
    control how Python invalidates hash-based .pyc files
file   : program read from script file
-      : program read from stdin (default; interactive mode if a tty)
arg ...: arguments passed to program in sys.argv[1:]

Other environment variables:
PYTHONSTARTUP: file executed on interactive startup (no default)
PYTHONPATH   : ':'-separated list of directories prefixed to the
               default module search path.  The result is sys.path.
PYTHONHOME   : alternate <prefix> directory (or <prefix>:<exec_prefix>).
               The default module search path uses <prefix>/lib/pythonX.X.
PYTHONPLATLIBDIR : override sys.platlibdir.
PYTHONCASEOK : ignore case in 'import' statements (Windows).
PYTHONUTF8: if set to 1, enable the UTF-8 mode.
PYTHONIOENCODING: Encoding[:errors] used for stdin/stdout/stderr.
PYTHONFAULTHANDLER: dump the Python traceback on fatal errors.
PYTHONHASHSEED: if this variable is set to 'random', a random value is used
   to seed the hashes of str and bytes objects.  It can also be set to an
   integer in the range [0,4294967295] to get hash values with a
   predictable seed.
PYTHONINTMAXSTRDIGITS: limits the maximum digit characters in an int value
   when converting from a string and when converting an int back to a str.
   A value of 0 disables the limit.  Conversions to or from bases 2, 4, 8,
   16, and 32 are never limited.
PYTHONMALLOC: set the Python memory allocators and/or install debug hooks
   on Python memory allocators. Use PYTHONMALLOC=debug to install debug
   hooks.
PYTHONCOERCECLOCALE: if this variable is set to 0, it disables the locale
   coercion behavior. Use PYTHONCOERCECLOCALE=warn to request display of
   locale coercion and locale compatibility warnings on stderr.
PYTHONBREAKPOINT: if this variable is set to 0, it disables the default
   debugger. It can be set to the callable of your debugger of choice.
PYTHONDEVMODE: enable the development mode.
PYTHONPYCACHEPREFIX: root directory for bytecode cache (pyc) files.
PYTHONWARNDEFAULTENCODING: enable opt-in EncodingWarning for 'encoding=None'.
grimwarg-picoctf@webshell:~$ python3 level1.py level1.flag.txt.enc 
Please enter correct password for flag: 
That password is incorrect

//read what's inside the python script
grimwarg-picoctf@webshell:~$ less level1.py                        
grimwarg-picoctf@webshell:~$ python3 level1.py level1.flag.txt.enc 
Please enter correct password for flag: 8713             
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}
grimwarg-picoctf@webshell:~$ 