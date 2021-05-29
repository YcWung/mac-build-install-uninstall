```bash
# LDFLAGS="-L/usr/local/lib" CPPFLAGS="-I/usr/local/include" DYNAMIC_ARCH=1 USE_OPENMP=1 NO_AVX512=1 make CC=gcc-10 FC=gfortran libs netlib shared
LDFLAGS="-L/usr/local/opt/gcc/lib/gcc/10" CPPFLAGS="-I/usr/local/opt/gcc/include" make DYNAMIC_ARCH=1 USE_OPENMP=1 NO_AVX512=1 CC="gcc-10" FC=gfortran libs netlib shared
# make CC=gcc-10 FC=gfortran USE_OPENMP=1
# LDFLAGS="-L/usr/local/lib,/usr/local/lib/gcc/10" CPPFLAGS="-I/usr/local/include" make NO_STATIC=1 USE_OPENMP=1 DYNAMIC_ARCH=1 NO_AVX512=1 CC=gcc-10 FC=gfortran libs shared
# LDFLAGS="-L/usr/local/opt/llvm/lib -Wl,-rpath,/usr/local/opt/llvm/lib" CPPFLAGS="-I/usr/local/opt/llvm/include" CEXTRALIB=lomp make DYNAMIC_ARCH=1 USE_OPENMP=1 NO_AVX512=1 CC="/usr/local/opt/llvm/bin/clang" FC=gfortran libs netlib shared
make install PREFIX=$HOME/third_party/OpenBLAS-0.3.10
cd $HOME/third_party/OpenBLAS-0.3.10
ln -s libopenblas.dylib libblas.dylib
ln -s libopenblas.dylib liblapack.dylib
cd -
```

