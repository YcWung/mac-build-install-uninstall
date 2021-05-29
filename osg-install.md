```bash
cmake -DCMAKE_INSTALL_PREFIX=$HOME/third_party/OpenSceneGraph-3.6.5 \
      -DCMAKE_BUILD_TYPE=Release \
      -DBUILD_SHARED_LIBS=ON \
      -DCMAKE_EXPORT_COMPILE_COMMANDS=ON \
      -DCMAKE_MACOSX_RPATH=ON \
      -DCMAKE_INSTALL_RPATH=$HOME/third_party/OpenSceneGraph-3.6.5/lib \
      -DCMAKE_INSTALL_RPATH_USE_LINK_PATH=TRUE \
      -DOSG_DEFAULT_IMAGE_PLUGIN_FOR_OSX=imageio \
      -DOSG_WINDOWING_SYSTEM=Cocoa \
      -B build -G Xcode
cmake --build build --config Release --target install
```

