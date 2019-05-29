Bootstrap: docker
From: centos

%setup
   echo ${SINGULARITY_ROOTFS}
   mkdir ${SINGULARITY_ROOTFS}/container
  
%post
   yum update -y
   yum groupinstall -y "Development Tools"
   yum install -y gcc
   yum install -y gcc-c++
   yum install -y wget
   yum install -y git
   yum install -y ca-certificates
   wget http://www.mpich.org/static/downloads/3.2.1/mpich-3.2.1.tar.gz
   tar xf mpich-3.2.1.tar.gz
   rm -f mpich-3.2.1.tar.gz
   cd mpich-3.2.1
   ./configure --prefix=$PWD/install --disable-wrapper-rpath
   make -j 4 install
   export PATH=$PATH:$PWD/install/bin
   export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$PWD/install/lib
   cd /container
   git clone https://github.com/LLNL/mpiBench
   cd mpiBench
   mpicc -o mpibench -fPIC mpiBench.c
   
%runscript
   /container/mpiBench/mpibench
   
