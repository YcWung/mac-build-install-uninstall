```bash
CMAKE_PREFIX_PATH="$HOME/third_party/SuiteSparse-5.8.1:$HOME/third_party/tbb-2020.3:$HOME/third_party/lapack-3.9.0:$HOME/third_party/metis-5.1.0:$HOME/third_party/glfw-3.3.2:$HOME/third_party/glew-2.2.0:$HOME/third_party/glm-0.9.9.8/cmake/glm" cmake -B build -S . -DCMAKE_INSTALL_PREFIX=$HOME/third_party/eigen-3.3.8
cd build
make install
```

