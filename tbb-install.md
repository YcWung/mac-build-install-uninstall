```bash
make
install build/macos_intel64_clang_cc12.0.0_os10.15.7_release/*.dylib $HOME/third_party/tbb-2020.3/lib/
cp -a include/tbb ~/third_party/tbb-2020.3/include
cmake -DINSTALL_DIR=$HOME/third_party/tbb-2020.3/lib/cmake/tbb-2020.3 \
      -DSYSTEM_NAME=Darwin \
      -DTBB_VERSION_FILE=$HOME/third_party/tbb-2020.3/include/tbb/tbb_stddef.h \
      -P cmake/tbb_config_installer.cmake
```

