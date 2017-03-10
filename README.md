Build kubernetes rpm binaries
-------------
```bash
# install gvm
bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
source /root/.gvm/scripts/gvm
# install golang
yum install bison gcc -y
gvm install go1.4 -B
gvm use go1.4
gvm install go1.8
gvm use go1.8 --default
# clone this repo
git clone --recursive https://github.com/mritd/kubernetes-rpm-builder
# you must install golang 1.6+ manually; no RPM currently available
yum install rpm-build etcd
yum groupinstall "Development Tools"
# make sure you have ample storage space available, both here and in /tm; 5GB is not enough
cd kubernetes-rpm-builder
./build_latest_stable_kubernetes.sh v1.5.4   # argument is the git tag to build
```

**准备好 8 核心 16G VPS，半小时时间等着你**

**如果可能请使用国外 VPS，譬如 DigitalOcean 之类的按小时计费的**

**一小时 2 块钱足够编译完，下面是推广时间: [DigitalOcean 邀请链接](https://m.do.co/c/942d5ae7a61c)**
