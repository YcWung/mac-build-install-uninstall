```bash
./autogen.sh
./configure --prefix=$HOME/third_party/djvulibre-3.5.28 \
    --disable-desktopfiles \
    --with-jpeg="$HOME/third_party/jpeg-9d" \
    --with-tiff="$HOME/third_party/tiff-4.1.0"
make
make install
```

