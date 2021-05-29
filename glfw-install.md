```bash
cmake -DCMAKE_INSTALL_PREFIX=$HOME/third_party/glfw-3.3.2 \
      -DCMAKE_INSTALL_LIBDIR=$HOME/third_party/glfw-3.3.2/lib \
      -DBUILD_SHARED_LIBS=ON \
      -B build -S . -G Xcode
cmake --build build --config Release
cmake --install build
```

