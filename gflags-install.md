```bash
cmake -S . -B cmake-build -DBUILD_SHARED_LIBS=ON -DCMAKE_EXPORT_COMPILE_COMMANDS=ON
cmake --build cmake-build --config Release
cmake --install cmake-build --prefix $HOME/third_party/gflags-2.2.2
```

