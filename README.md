# Android kernel for exynos7270
## ATTENTION! YOUR WARRANTY IS NOW VOID
Kernel source for Gear S3 devices, optimized for running android platform.  
This source will likely hard brick your device, use the download links or the stable branch below to download stable compiled kernel.
For tizen kernel, use the tizen-kernel branch.

## Build instructions
1. Prepare the build environment  
	```$ sudo apt-get install build-essential kernel-package libncurses5-dev bzip2```
2. Clone this branch  
	```$ git clone -b master https://github.com/DrBrunkov/AW-exynos7270-kernel.git```
3. Export tools to PATH  
	```$ export CROSS_COMPILE=toolchains/aarch64-linux-android-4.9/prebuilt/linux-x86_64/bin/aarch64-linux-android-```  
	```$ export ARCH=arm64```
4. Prepare and build headers  
	```$ make distclean```  
	```$ make mrproper```  
	```$ make headers_check```  
	```$ make headers_install INSTALL_HDR_PATH=uapi-headers/usr```  
5. Build the kernel  
	```$ chmod a+x ./scripts/exynos_dtbtool.sh```  
	```$ chmod a+x ./scripts/exynos_mkdzimage.sh```  
	```$ cp /usr/lib/gcc-cross/aarch64-linux-gnu/5/libgcc.a toolchains/aarch64-linux-android-4.9/prebuilt/linux-x86_64/lib/gcc/aarch64-linux-android/4.9.x```  
	```$ make tizen_solis_defconfig  //For SM-R760, SM-R770```  
	```$ make tizen_solis_defconfig_lte  //For SM-R765```  
	```$ make Image```  
	```$ ./scripts/exynos_dtbtool.sh -o arch/arm64/boot/merged-dtb -p scripts/dtc/ -v arch/arm64/boot/dts/```  
	```$ ./scripts/exynos_mkdzimage.sh -o arch/arm64/boot/dzImage -k arch/arm64/boot/Image -d arch/arm64/boot/merged-dtb```  
## Download links
* LTE version: TBD
* All others: TBD
