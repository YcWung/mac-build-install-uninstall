```bash
cmake -S . -B build \
      -DBUILD_SHARED_LIBS=ON \
      -DBUILD_TESTING=OFF \
      -DCMAKE_INSTALL_PREFIX=$HOME/third_party/lapack-3.9.0 \
      -DCMAKE_INSTALL_RPATH=$HOME/third_party/lapack-3.9.0/lib \
      -DCMAKE_MACOSX_RPATH=ON \
      -DCMAKE_C_COMPILER=gcc-10 \
      -DCMAKE_Fortran_COMPILER=gfortran \
      -DLAPACKE=ON \
      -DCBLAS=ON
#      -DCMAKE_SKIP_RPATH=ON \
#      -DBUILD_DEPRECATED=ON
cmake --build build --config Release --target install
```

