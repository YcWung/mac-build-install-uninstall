```bash
cputype=$(uname -m | sed "s/\\ /_/g")
systype=$(uname -s)
BUILDDIR=build/${systype}-${cputype}
cmake -S . -B $BUILDDIR \
      -DCMAKE_EXPORT_COMPILE_COMMANDS=ON \
      -DCMAKE_VERBOSE_MAKEFILE=1 \
      -DCMAKE_BUILD_TYPE=Release \
      -DGKLIB_PATH=$HOME/third_party_sources/metis-5.1.0/GKlib \
      -DCMAKE_INSTALL_PREFIX=$HOME/third_party/metis-5.1.0 \
      -DSHARED=1 \
      -DCMAKE_INSTALL_RPATH=$HOME/third_party/metis-5.1.0/lib \
      -DCMAKE_MACOSX_RPATH=ON
make -C $BUILDDIR install
# or just
make install
```

