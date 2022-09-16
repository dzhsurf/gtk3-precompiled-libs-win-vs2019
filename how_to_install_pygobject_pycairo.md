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

