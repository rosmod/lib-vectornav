vn100 library
==============

Install Build Tools
-------------------------

```bash
sudo apt-get install python-catkin-tools
```

Build Library:
-------------

```bash
cd
mkdir catkin_ws #if a workspace does not already exist
cd catkin_ws
git clone https://github.com/rosmod/lib-vectornav.git src/lib-vectornav
catkin build vectornav
```

Update Library:
-----------------

```bash
cd ~/catkin_ws
catkin clean vectornav
cd src/lib-vectornav
git pull
cd ..
catkin build vectornav
```


Rosmod Source Library Setup:
-------------------------------

1. In this github repo navigate to [releases](https://github.com/rosmod/lib-vectornav/releases), right click on `vectornav.zip` (not the source code zip!) and select `Copy link address'
2. In a rosmod project, drag in a new source library to the software model
3. Paste the link in the url attribute
4. Name the source library `vectornav`
5. Drag the library into the `set editor` of any component that uses it
6. In the forwards section of the component add `#include "vectornav/vn100.h"`



