### Ubuntu Slim
#### Reference: (https://hub.docker.com/r/arm64v8/ubuntu/)
```
mkdir ROOTFS
cp ubuntu-xenial-core-cloudimg-arm64-root-orig.tar.gz ROOTFS/ubuntu-xenial-core-cloudimg-arm64-root.tar.gz
cd ROOTFS
sudo tar zxf ubuntu-xenial-core-cloudimg-arm64-root.tar.gz
sudo rm usr/share/doc/* usr/share/locale/* usr/share/man/* usr/share/info/* usr/share/lintian/* *.tar.gz -fR
sudo tar zcf ubuntu-xenial-core-cloudimg-arm64-root.tar.gz *
mv ubuntu-xenial-core-cloudimg-arm64-root.tar.gz ..
cd ..
sudo chown -R $USER. ubuntu-xenial-core-cloudimg-arm64-root.tar.gz
sudo rm ROOTFS/ -fR
```

```
docker build -t izone/arm64v8:xenial-slim ./xenial-slim/
```

