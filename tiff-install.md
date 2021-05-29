```bash
./configure --prefix=$HOME/third_party/tiff-4.1.0 \
            --disable-dependency-tracking \
            --disable-lzma \
            --with-jpeg-include-dir=$HOME/third_party/jpeg-9d/include \
            --with-jpeg-lib-dir=$HOME/third_party/jpeg-9d/lib \
            --without-x
make install
```

