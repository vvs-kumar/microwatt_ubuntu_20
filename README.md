DOWNLOAD ghdl,micropython,microwatt and powerpc64le-power8(from Anton Blanchard github page)

mkdir /home/$USER/uwatt
cd ../

Download powerpc64le-power8(from Anton Blanchard github page)

wget https://toolchains.bootlin.com/downloads/releases/toolchains/powerpc64le-power8/tarballs/powerpc64le-power8--glibc--stable-2021.11-1.tar.bz2
tar -xvf powerpc64le-power8--glibc--stable-2021.11-1.tar.bz2

Creeating Clone from Github Pages:

git clone https://github.com/ghdl/ghdl.git
git clone https://github.com/micropython/micropython.git
git clone https://github.com/antonblanchard/microwatt

You will get all folders in uwatt folder.

Setting path for powerpcle64

export PATH=$PATH:/home/$USER/uwatt/powerpc64le-power8--glibc--stable-2021.11-1/bin
export CROSS_COMPILE=powerpc64le-linux-

getting into powerpc folder and make micropython.

cd micropython/ports/powerpc
sudo apt install make
make -j$(nproc)
cd ../../../

Installing libraries:

sudo apt install llvm clang gnat zlib1g-dev

Check above for Proper installation

wget http://archive.ubuntu.com/ubuntu/pool/universe/g/gnat-4.9/gnat-4.9-base_4.9.3-3ubuntu5_amd64.deb
wget http://archive.ubuntu.com/ubuntu/pool/universe/g/gnat-4.9/libgnat-4.9_4.9.3-3ubuntu5_amd64.deb
sudo dpkg -i ./gnat-4.9-base_4.9.3-3ubuntu5_amd64.deb
sudo dpkg -i ./libgnat-4.9_4.9.3-3ubuntu5_amd64.deb

Installing GHDL Simulator:

cd ghdl
mkdir -p /home/$USER/uwatt/ghdl_build
mkdir build && cd build
../configure --with-llvm-config --prefix=/home/$USER/uwatt/ghdl_build
make
make install
cd ../../

make Microwatt:

cd microwatt
make



CHECK FOR REFERENCE
https://asciinema.org/a/364414


