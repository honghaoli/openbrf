OpenBRF _by Marco Tarini_ (MacOS Port)
------------------------

A modding tool used to view, edit and convert the proprietary _Binary Resource files_ (BRFs) loaded by the popular «Mount&Blade» and «Mount&Blade: Warband» games.

The original source code ZIP file at [talewords forum](https://forums.taleworlds.com/index.php?topic=72279.0)

This repo is forked from Linux version [cfcohen/openbrf](https://github.com/cfcohen/openbrf)

### What I changed for MacOS
1. Change GL to OpenGL
    ```
    #include <GL/glu.h>
    #include <OpenGL/glu.h>
    ```
2. Some system dependent functions:
    - change stricmp() to strcasecmp()
    - change platform.cpp to include MacOS

### Build instructions for MacOS
1. First Download the [VCGLIB](https://github.com/cnr-isti-vclab/vcglib)
2. Then change the VCGLIB path in `openBrf.pro` to your own folder
    ```
    VCGLIB = /home/cory/Source/VCGLib
    ```
3. Download/Install `Qt5`!
    ```
    qmake -makefile openBrf.pro
    make
    ```
4. (Optional) run it overriding the float dot notation so that it can load `carry_positions.txt` in other languages other than English
    ```
    env LC_NUMERIC=C ./openBrf
    ```

### Note
1. A `reference.brf` file should be under `../Module/Native/` to use animation skeleton references.
2. A `skeleton_bodies.xml` file should be under `../Module/Native/Data/` to use the hitboxes.

### License
This code and the original ZIP file are licensed under the _GNU
General Public License_, according to the
[talewords forum](https://forums.taleworlds.com/index.php?topic=72279.0)