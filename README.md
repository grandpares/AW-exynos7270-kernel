# Tizen kernel for exynos7270
## ATTENTION! YOUR WARRANTY IS NOW VOID
Kernel source for Gear S3 devices, optimized for running android platform.  
This source will likely hard brick your device, use the download links or the stable branch below to download stable compiled kernel.
For tizen kernel, use the tizen-kernel branch.

## DO NOT FLASH! 
This source is unfinished. It contains no recovery environment, which means your watch will be unable to talk to odin. Furthermore, it will not boot tizen OR android. Developers should use quemu for testing until the kernel boots to some state, otherwise it's just a waste of testing devices.

## Build instructions
1. Prepare the build environment  
	```$ sudo apt-get install build-essential kernel-package libncurses5-dev bzip2```
2. Clone this branch  
	```$```
3. Export tools to PATH  
	```$ export CROSS_COMPILE=aarch64-lunux-gnu-```  
	```$ export ARCH=arm64```
4. Prepare and build headers  
	```$ make distclean```  
	```$ make mrproper```  
	```$ make headers_check```  
	```$ make headers_install INSTALL_HDR_PATH=uapi-headers/usr```  
5. Build the kernel  
	```$ make tizen_solis_defconfig  //For SM-R760, SM-R770```  
	```$ make tizen_solis_defconfig_lte  //For SM-R765```  
	```$ make Image```  
	```$ ./scripts/exynos_dtbtool.sh -o arch/arm64/boot/merged-dtb -p scripts/dtc/ -v arch/arm64/boot/dts/```  
	```$ ./scripts/exynos_mkdzimage.sh -o arch/arm64/boot/dzImage -k arch/arm64/boot/Image -d arch/arm64/boot/merged-dtb```  
## Download links
* LTE version: TBD
* All others: TBD
