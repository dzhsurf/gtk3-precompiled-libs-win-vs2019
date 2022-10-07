How to install PyGObject, PyCairo using local precompiled GTK-3 environment
===============================================================

* Download `precompiled-sdk.zip`, extract `bin` directory and set it to `PATH` environment variables.

* Copy `pygobject-pycairo-deps\include`, `pygobject-pycairo-deps\lib` to your `Python` environment directory. For example, in miniconda python environment, the `include` path is `{CONDA_PATH}\envs\{ENV_NAME}\include`, and `lib` path is `{CONDA_PATH}\envs\{ENV_NAME}\libs`

* Config `GI_TYPELIB_PATH` environment variable.

  ```shell
  set GI_TYPELIB_PATH={YOURPATH}\lib\girepository-1.0
  ```

* Force reinstall `pycairo` 

  ```shell
  pip install --force-reinstall -no-binary :all: pycairo
  ```

* Now you can run your scripts.



Or you can use python wheel to install prebuilt GTK libraries. Only support Py3.7 ~ Py3.10.

```shell
pip install --no-binary --force-reinstall :all: pygobject-pycairo-prebuilt-libraries-vs2019
```

How this `pygobject-pycairo-prebuilt-libraries-vs2019` package work?

There're prebuilt pygobject, pycairo packages in it, when you setup this package, it will install the pygobject.whl, pycairo.whl  and copy all the prebuilt GTK DLLs to your environment.

Then, you can fix the DLL module path by import this module.

```python
import platform
try:
  from pygobject_prebuilt_deps import import_pygobject_dll_module
  	import_pygobject_dll_module()
except ImportError:
  pass

import gi
import cairo
gi.request_version("GTK", "3.0")
```

Then `import_pygobject_dll_module` function will add DLLs path to `os.environ['PATH']` and setup the `GI_TYPELIB_PATH` environment, so that you can easily to import gi and cairo.