OpenBRF _by Marco Tarini_ (MacOS Port)
------------------------

A modding tool used to view, edit and convert the proprietary _Binary Resource files_ (BRFs) loaded by the popular «Mount&Blade» and «Mount&Blade: Warband» games.

This GitHub repo was last updated from the source code ZIP file at:

https://forums.taleworlds.com/index.php?topic=72279.0

and modified to compile under Unix.

### For MacOS
I fixed many problems for MacOS, for example: 
1. change GL to OpenGL
    #include <GL/glu.h>
    #include <OpenGL/glu.h>
2. some system dependent functions:
    - change stricmp() to strcasecmp()
    - change platform.cpp to include MacOS

### Build instructions for MacOS:
    # First Download the [VCGLIB](https://github.com/cnr-isti-vclab/vcglib)
    # Then change the VCGLIB path in openBrf.pro to your own folder
    VCGLIB = /home/cory/Source/VCGLib

    # Requires Qt5!
    qmake -makefile openBrf.pro
    make
    
    # run it overriding the float dot notation so that it can load
    # `carry_positions.txt` in other languages other than English
    env LC_NUMERIC=C ./openBrf

Alternatively there's also a ready-to-use _AUR_ package that might come in handy if you are using _Arch Linux_ (helpfully provided by Swyter):

https://aur.archlinux.org/packages/openbrf/

### License
This code and the original ZIP file are licensed under the _GNU
General Public License_, according to the dicussion forum:

https://forums.taleworlds.com/index.php?topic=72279.0
