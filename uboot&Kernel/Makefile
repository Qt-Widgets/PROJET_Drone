ARCH ?= arm
CROSS_COMPILE ?= /home/texierp/PROJET_Drone/gcc-linaro-arm-linux-gnueabihf-4.7-2013.01-20130125_linux/bin/arm-linux-gnueabihf-
KERNEL_DIR ?= /home/texierp/a20_kernel_3.4_DRONE/linux-sunxi
CFLAGS := -O3 -march=armv7-a -mcpu=cortex-a7 -mtune=cortex-a7 -mfpu=neon-vfpv4 -mfloat-abi=hard

.PHONY: uImage modules help
uImage::
	@echo "Création du dossier config_`date +\%d-%m-%y_%X`"
	mkdir -p ${KERNEL_DIR}/LOG/config_`date +\%d-%m-%y_%X`
	cp -f ${KERNEL_DIR}/.config ${KERNEL_DIR}/LOG/config_`date +\%d-%m-%y_%X`/config_`date +\%d-%m-%y_%X`.txt
	${MAKE} -C ${KERNEL_DIR} ARCH=${ARCH} CROSS_COMPILE=${CROSS_COMPILE} -j2 uImage

modules::
	${MAKE} -C ${KERNEL_DIR} ARCH=${ARCH} CROSS_COMPILE=${CROSS_COMPILE} -j2 INSTALL_MOD_PATH=/home/texierp/a20_kernel_3.4_DRONE/linux-sunxi modules
	su -c '${MAKE} -C ${KERNEL_DIR} ARCH=${ARCH} CROSS_COMPILE=${CROSS_COMPILE} -j2 INSTALL_MOD_PATH=/home/texierp/a20_kernel_3.4_DRONE/linux-sunxi modules install'

help::
	@echo "\n\tMakefile permettant de générer l'image kernel"
	@echo "\n"
