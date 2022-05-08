# toolboxs-autoscript-gcc9.3.0

# 1、利用 ppa:ubuntu-toolchain-r/test 源安装gcc9.3.0
一.安装如下命令可以安装g++9.3.0
```
 sudo apt-get update && \
 sudo apt-get install build-essential software-properties-common -y && \
 sudo add-apt-repository ppa:ubuntu-toolchain-r/test -y && \
 sudo apt-get update && \
 sudo apt-get install gcc-snapshot -y && \
 sudo apt-get update && \
 sudo apt-get install gcc-9 g++-9 -y && \
 sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 60 --slave /usr/bin/g++ g++ /usr/bin/g++-9
二.安装好g++9.3.0后保存默认的g++5
 sudo apt-get install gcc-5 g++-5 -y && \
 sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-5 60 --slave /usr/bin/g++ g++ /usr/bin/g++-5;
 ```




# 2、安装GCC-9.3.0全指导



# 下载

```
wget https://mirrors.tuna.tsinghua.edu.cn/gnu/gcc/gcc-9.3.0/gcc-9.3.0.tar.gz

tar -xvf gcc-9.3.0.tar.gz

cd gcc-9.3.0

wget https://mirrors.tuna.tsinghua.edu.cn/gnu/gmp/gmp-6.1.0.tar.xz


tar -xvf gmp-6.1.0.tar.xz


mv gmp-6.1.0 gmp


wget https://mirrors.tuna.tsinghua.edu.cn/gnu/mpfr/mpfr-3.1.4.tar.gz


tar -xvf mpfr-3.1.4.tar.gz


mv mpfr-3.1.4 mpfr



wget https://mirrors.tuna.tsinghua.edu.cn/gnu/mpc/mpc-1.0.3.tar.gz


tar -xvf mpc-1.0.3.tar.gz


mv mpc-1.0.3 mpc
```


# 安装编译

```
mkdir gcc-build

cd gcc-build



（/usr/local/gcc-9.3.0是新版本GCC的安装目录，可以更换，新手不推荐更换）

../configure --prefix=/usr/local/gcc-9.3.0 --disable-multilib --enable-languages=c,c++
```

2 编译

(小伙伴电脑有CPU多个核心时，推荐把“4”换成自己的核心数，这个过程需要时间多)

```
make -j 4

```

3 安装

```
make install -j 4

```

4 更新链接配置

```
 ln -s /usr/local/gcc-9.3.0 /usr/local/gcc

 export PATH=/usr/local/gcc/bin:$PATH


export LD_LIBRARY_PATH=/usr/local/gcc/lib64

export MANPATH=/usr/local/gcc/share/man:$MANPATH

```

三.成果检验

```
gcc -v

```
