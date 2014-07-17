OpenNI2-Linux-Arm-Cubieboard2
=============================

OpenNI v2.3 for Cubieboard2

Install the following dependencies:

sudo apt-get install git g++ make python libusb-1.0-0-dev libudev-dev pkg-config
clone OpenNI2

git clone https://github.com/OpenNI/OpenNI2
cd OpenNI2
edit ThirdParty/PSCommon/BuildSystem/Platform.Arm

nano ThirdParty/PSCommon/BuildSystem/Platform.Arm
and replace

CFLAGS += -march=armv7-a -mtune=cortex-a9 -mfpu=neon -mfloat-abi=softfp #-mcpu=cortex-a8
with

CFLAGS += -march=armv7-a -mtune=cortex-a9 -mfpu=neon -mfloat-abi=hard
then run make to compile the OpenNI2 drivers and libraries

PLATFORM=Arm make
