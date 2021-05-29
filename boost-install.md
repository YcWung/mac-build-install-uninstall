```bash
./bootstrap.sh --prefix=$HOME/third_party/boost_1_74_0 \
               --without-libraries=python,mpi
./b2 install link=shared \
     cxxflags=-std=c++14 \
     cxxflags=-stdlib=libc++ linkflags=-stdlib=libc++
```

