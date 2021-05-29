```bash
CMAKE_PREFIX_PATH="$HOME/third_party/glog-0.4.0:$HOME/third_party/gflags-2.2.2:$HOME/third_party/SuiteSparse-5.8.1:$HOME/third_party/tbb-2020.3:$HOME/third_party/eigen-3.3.8:$HOME/third_party/lapack-3.9.0" cmake \
      -S . -B cmake-build \
      -DBUILD_SHARED_LIBS=ON \
      -DCMAKE_EXPORT_COMPILE_COMMANDS=ON \
      -DCMAKE_BUILD_TYPE=Release \
      -DBUILD_TESTING=OFF \
      -DBUILD_EXAMPLES=OFF \
      -DMETIS_LIBRARY=$HOME/third_party/metis-5.1.0/lib/libmetis.dylib \
      -DCXX11=ON \
      -DTBB=ON \
      -DCMAKE_INSTALL_RPATH_USE_LINK_PATH=TRUE \
      -DCMAKE_MODULE_PATH=$HOME/third_party/cmake-modules
      # -DCMAKE_FIND_PACKAGE_PREFER_CONFIG=TRUE
      # -DCMAKE_C_COMPILER=gcc-10 \
      # -DCMAKE_CXX_COMPILER=g++-10 \
      # -DOPENMP=ON \
cmake --build cmake-build --config Release
cmake --install cmake-build --prefix $HOME/third_party/ceres-solver-1.14.0
```

Question:

- how to link to self-built lapack rather than that of system?
- how to build with GCC?