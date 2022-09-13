# yocto-lec-imx6

Yocto Project for Adlink LEC-iMX6

## Install applications that you will need to build and yocto project

sudo apt install gawk wget git diffstat unzip texinfo gcc build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev zstd liblz4-tool

## Clone Poky

``
git clone git://git.yoctoproject.org/poky
``

Select the proper branch

See what branch you are on (probably the repos default branch)

``
git status
``

See what branches are available to check out

``
git branch -r
``

Switch to the branch you want (if branch is no longer supported, you will get a detached head warning because the yocto project is no longer updating it, eol)

``
git checkout origin/zeus
``

To check for updates

``
git pull
``

## Create a build directory

``
cd poky
``

``
source oe-init-build-env \<builddirectoryname\>
``

May get instructed to install python 2 or 3

``
sudo apt install python2
``

Run bitbake and let it build. It will take 3 or 4 hours on a laptop with an i5 processor

``
bitbake core-image-sato
``

Check for errors. If you get warnings then research them to see if will cause problems down the road

The machine you built for is a qemux (quick emulator) type.run the simulations

``
runqemu qemux86-64
``

The emulation will run slow. You can use it to check your builds to see if every application and libraries are getting built in the image you're creating.
When we add the bsp layer you will have to run this image on the actual hardware.
So work out the little "non-hardware" issues using the qemu machine.

