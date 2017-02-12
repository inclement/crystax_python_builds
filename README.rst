
CrystaX Python builds
=====================

This repository hosts the files needed for CrystaX to build versions
of Python that aren't yet built in.

For now, the extra files support only Python 3.6.

The releases for this repository include prebuilt Python versions for
some target architectures, which can simply be extracted and copied
directly into place.

Instructions
============

1) Download the ``CrystaX NDK <https://www.crystax.net/en/android/ndk>`` to some path ``$NDK_DIR``.
2) Copy android.mk.3.6, config.c.3.6 and interpreter.c.3.6 to ``$NDK_DIR/build/tools/build-target-python
3) Create the Python 3.6 dir: ``mkdir $NDK_DIR/sources/python/3.6
4) Copy the Android.mk into place: ``cp Android.mk.3.6 $NDK_DIR/sources/python/3.6``
5) Download the Python 3.6.0 source to some path ``$PYTHON_DIR``
5) Run the ``build-target-python.sh`` script: ``$NDK_DIR/build/tools/build-target-python.sh --ndk_dir=$NDK_DIR --abis=armeabi-v7a -j5 --verbose $PYTHON_DIR``. You can also try a different abi.

This should build Python for the target architecture and copy it into
place so that it can be used like any other.
