# toolboxs-autoscript-gcc9.3.0
安装GCC-9.3.0全指导



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
