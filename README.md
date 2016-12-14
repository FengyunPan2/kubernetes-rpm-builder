Build kubernetes rpm binaries
-------------
```bash
git clone --recursive https://github.com/mritd/kubernetes-rpm-builder
# you must install golang 1.6+ manually; no RPM currently available
sudo yum install rpm-build etcd
sudo yum groupinstall "Development Tools"
# make sure you have ample storage space available, both here and in /tm; 5GB is not enough
cd kubernetes-rpm-builder
./build_latest_stable_kubernetes.sh v1.5.1   # argument is the git tag to build
```

**准备好 8 核心 16G VPS，半小时时间等着你**

**如果可能请使用国外 VPS，譬如 DigitalOcean 之类的按小时计费的**

**一小时 2 块钱足够编译完，下面是推广时间: [DigitalOcean 邀请链接](https://m.do.co/c/942d5ae7a61c)**
