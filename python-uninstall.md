```bash
sudo rm -rf "/Applications/Python 3.8"
sudo rm -rf "/Library/Frameworks/Python.framework"
cd /usr/local/bin
ls -l /usr/local/bin | grep '../Library/Frameworks/Python.framework/Versions/3.8' | awk '{print $9}' | tr -d @ | xargs rm
```

then edit `.profile` to remove PATH entry