python 3.8 virtualenv

```bash
# cd $HOME/venv/
# python3 -m venv cv
python3 -m pip install --user virtualenv
$HOME/Library/Python/3.8/bin/virtualenv -p python3 $HOME/venv/cv
source $HOME/venv/cv/bin/activate
pip install numpy
```

Why can't

```bash
python3 -m venv $HOME/venv/cv
```

Compile:

```bash
source $HOME/venv/cv/bin/activate

CONTRIB_DIR="$HOME/third_party_sources/opencv_contrib-4.4.0"
LAPACK_DIR="$HOME/third_party/lapack-3.9.0"
PY3_INC_DIR="/Applications/Xcode.app/Contents/Developer/Library/Frameworks/Python3.framework/Versions/3.8/include/python3.8"
PY3_LIB="/Applications/Xcode.app/Contents/Developer/Library/Frameworks/Python3.framework/Versions/3.8/lib/libpython3.8.dylib"

export CMAKE_PREFIX_PATH="$HOME/third_party/protobuf-3.13.0:$HOME/third_party/glog-0.4.0:$HOME/third_party/gflags-2.2.2:$HOME/third_party/SuiteSparse-5.8.1:$HOME/third_party/tbb-2020.3:$HOME/third_party/eigen-3.3.8:$HOME/third_party/lapack-3.9.0:$HOME/third_party/ceres-solver-1.14.0:$HOME/third_party/glfw-3.3.2:$HOME/third_party/glew-2.1.0:$HOME/third_party/glm-0.9.9.8/cmake/glm:$HOME/third_party/jpeg-9d:$HOME/third_party/libpng-1.6.37:$HOME/third_party/tiff-4.1.0:$HOME/third_party/metis-5.1.0"

cmake -S . -B build \
      -DCMAKE_EXPORT_COMPILE_COMMANDS=ON \
      -DCMAKE_INSTALL_PREFIX="$HOME/third_party/opencv-4.4.0" \
      -DBUILD_SHARED_LIBS=ON \
      -DCMAKE_BUILD_TYPE=Release \
      -DBUILD_DOCS=ON \
      -DBUILD_JASPER=OFF \
      -DBUILD_JAVA=OFF \
      -DBUILD_JPEG=OFF \
      -DBUILD_OPENEXR=OFF \
      -DBUILD_PERF_TESTS=OFF \
      -DBUILD_PNG=OFF \
      -DBUILD_PROTOBUF=OFF \
      -DBUILD_TESTS=OFF \
      -DBUILD_TIFF=OFF \
      -DBUILD_WEBP=OFF \
      -DBUILD_ZLIB=OFF \
      -DBUILD_opencv_hdf=OFF \
      -DBUILD_opencv_java=OFF \
      -DBUILD_opencv_text=ON \
      -DOPENCV_ENABLE_NONFREE=ON \
      -DOPENCV_EXTRA_MODULES_PATH=$CONTRIB_DIR/modules \
      -DOPENCV_GENERATE_PKGCONFIG=ON \
      -DPROTOBUF_UPDATE_FILES=ON \
      -DWITH_1394=OFF \
      -DWITH_CUDA=OFF \
      -DWITH_EIGEN=ON \
      -DWITH_FFMPEG=OFF \
      -DWITH_WEBP=OFF \
      -DWITH_GPHOTO2=OFF \
      -DWITH_GSTREAMER=OFF \
      -DWITH_JASPER=OFF \
      -DWITH_OPENEXR=OFF \
      -DWITH_OPENGL=OFF \
      -DWITH_QT=OFF \
      -DWITH_TBB=ON \
      -DWITH_VTK=OFF \
      -DBUILD_opencv_python2=OFF \
      -DBUILD_opencv_python3=ON \
      -DPYTHON3_EXECUTABLE="$VIRTUAL_ENV/bin/python" \
      -DPYTHON3_INCLUDE_DIR="$PY3_INC_DIR" \
      -DPYTHON3_LIBRARY="$PY3_LIB" \
      -DPYTHON3_NUMPY_INCLUDE_DIRS="$VIRTUAL_ENV/lib/python3.8/site-packages/numpy/core/include" \
      -DOPENCV_PYTHON3_INSTALL_PATH="$VIRTUAL_ENV/lib/python3.8/site-packages" \
      -DLAPACK_LIBRARIES="$LAPACK_DIR/lib/liblapack.dylib;$LAPACK_DIR/lib/libblas.dylib;$LAPACK_DIR/lib/libcblas.dylib" \
      -DLAPACK_CBLAS_H="$LAPACK_DIR/include/cblas.h" \
      -DLAPACK_LAPACKE_H="$LAPACK_DIR/include/lapacke.h" \
      # -DCMAKE_OSX_DEPLOYMENT_TARGET= \
      # -DENABLE_AVX=OFF \
      # -DENABLE_AVX2=OFF \
      # -DENABLE_SSE41=OFF \
      # -DENABLE_SSE42=OFF
      
cmake --build build --config Release --target install
# cmake --build build --config Release
# cmake --install build --prefix $HOME/third_party/opencv-4.4.0
```

Note:

- OpenGL not supported on Apple

Question:

- 