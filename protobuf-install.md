```bash
export CXXFLAGS="-DNDEBUG $CXXFLAGS -std=c++11"
./configure --prefix=$HOME/third_party/protobuf-3.13.0 --disable-debug --disable-dependency-tracking --with-zlib
make
make install
```

