GTK3 Precompiled Libs For Native Windows
=============================

1. Download `x86/vs16` `precompiled-sdk.zip`
2. Extract `bin` and set the environment PATH variable.
3. Run `bin\gtk3-demo.exe` check everything goes work.
4. Copy the DLLs you need to your project.

**Notice:**

* The author only tested on VS2019 x86. The x64 or any other vs version may have some compile issue, or there's not, if you need the x64 version, try it yourself, bless you. 
* You should prepare VS2019 runtime for using these libs.

  

[How to install PyGObject, PyCairo with VS16 GTK-3](how_to_install_pygobject_pycairo.md)

[How to build GTK-3 for Native Windows(msvc), not msys, mingw, cywin, etc...](how_to_build_vs16_gtk3_libs.md)

