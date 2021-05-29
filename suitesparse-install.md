```bash
cmake -S GraphBLAS -B GraphBLAS/build

make library INSTALL="$HOME/third_party/SuiteSparse-5.8.1" \
             BLAS="-L$HOME/third_party/lapack-3.9.0/lib -Wl,-rpath,$HOME/third_party/lapack-3.9.0/lib -lblas" \
             LAPACK="-L$HOME/third_party/lapack-3.9.0/lib -Wl,-rpath,$HOME/third_party/lapack-3.9.0/lib -llapack" \
             TBB="-L$HOME/third_party/tbb-2020.3/lib -Wl,-rpath,$HOME/third_party/tbb-2020.3/lib -ltbb" \
             MY_METIS_LIB="-L$HOME/third_party/metis-5.1.0/lib -Wl,-rpath,$HOME/third_party/metis-5.1.0/lib -lmetis" \
             MY_METIS_INC="$HOME/third_party/metis-5.1.0/include"
             
make install INSTALL="$HOME/third_party/SuiteSparse-5.8.1" \
             BLAS="-L$HOME/third_party/lapack-3.9.0/lib -Wl,-rpath,$HOME/third_party/lapack-3.9.0/lib -lblas" \
             LAPACK="-L$HOME/third_party/lapack-3.9.0/lib -Wl,-rpath,$HOME/third_party/lapack-3.9.0/lib -llapack" \
             TBB="-L$HOME/third_party/tbb-2020.3/lib -Wl,-rpath,$HOME/third_party/tbb-2020.3/lib -ltbb" \
             MY_METIS_LIB="-L$HOME/third_party/metis-5.1.0/lib -Wl,-rpath,$HOME/third_party/metis-5.1.0/lib -lmetis" \
             MY_METIS_INC="$HOME/third_party/metis-5.1.0/include"
```



Old:

```bash
cmake -S GraphBLAS -B GraphBLAS/build
LDFLAGS="-Wl,-rpath,$HOME/third_party/lapack-3.9.0/lib,-rpath,$HOME/third_party/tbb-2020.3/lib,-rpath,$HOME/third_party/metis-5.1.0/lib" \
make library INSTALL="$HOME/third_party/SuiteSparse-5.8.1" \
             BLAS="-L$HOME/third_party/lapack-3.9.0/lib -lblas" \
             LAPACK="-L$HOME/third_party/lapack-3.9.0/lib -llapack" \
             TBB="-L$HOME/third_party/tbb-2020.3/lib -ltbb" \
             MY_METIS_LIB="-L$HOME/third_party/metis-5.1.0/lib -lmetis" \
             MY_METIS_INC="$HOME/third_party/metis-5.1.0/include"
             
LDFLAGS="-Wl,-rpath,$HOME/third_party/lapack-3.9.0/lib,-rpath,$HOME/third_party/tbb-2020.3/lib,-rpath,$HOME/third_party/metis-5.1.0/lib" \
make install INSTALL="$HOME/third_party/SuiteSparse-5.8.1" \
             BLAS="-L$HOME/third_party/lapack-3.9.0/lib -lblas" \
             LAPACK="-L$HOME/third_party/lapack-3.9.0/lib -llapack" \
             TBB="-L$HOME/third_party/tbb-2020.3/lib -ltbb" \
             MY_METIS_LIB="-L$HOME/third_party/metis-5.1.0/lib -lmetis" \
             MY_METIS_INC="$HOME/third_party/metis-5.1.0/include"
```

