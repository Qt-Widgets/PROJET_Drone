ARCH ?= arm
CROSS_COMPILE ?= /home/texierp/PROJET_Drone/gcc-linaro-arm-linux-gnueabihf-4.7-2013.01-20130125_linux/bin/arm-linux-gnueabihf-
KERNEL_DIR ?= /home/$USERNAME/a20_kernel_3.4_DRONE/linux-sunxi
CFLAGS := -O3 -march=armv7-a -mcpu=cortex-a7 -mtune=cortex-a7 -mfpu=neon-vfpv4 -mfloat-abi=hard

.PHONY: all
all::
    mkdir ${KERNEL_DIR}/LOG/$(date +%d-%m-%Y)
    cp -f ${KERNEL_DIR}/.config cp -f ${KERNEL_DIR}/LOG/$(date +%d-%m-%Y)
    ${MAKE} -C ${KERNEL_DIR} ARCH=${ARCH} CROSS_COMPILE=${CROSS_COMPILE} -j2 uImage
