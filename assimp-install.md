```bash
cmake -S . -B build \
      -DCMAKE_BUILD_TYPE=Release \
      -DASSIMP_BUILD_TESTS=OFF \
      -DCMAKE_EXPORT_COMPILE_COMMANDS=ON \
      -DCMAKE_INSTALL_RPATH_USE_LINK_PATH=TRUE \
      -DCMAKE_INSTALL_PREFIX="$HOME/third_party/assimp-5.0.1"
cmake --build build --target install
install_name_tool -add_rpath $HOME/third_party/assimp-5.0.1/lib \
                  $HOME/third_party/assimp-5.0.1/lib/libassimp.dylib
```

