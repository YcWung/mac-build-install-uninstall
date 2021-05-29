```bash
sed '/VERSION=[0-9]\{1,\}\(\.[0-9]\{1,\}\)\{2\}/a \
export PATH=\"\$HOME/third_party/djvulibre-3.5.28/bin:\$PATH\"
' djvu2pdf >> $HOME/.local/bin/djvu2pdf

chmod a+x $HOME/.local/bin/djvu2pdf
```

