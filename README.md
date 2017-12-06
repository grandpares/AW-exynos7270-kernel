# Android kernel for exynos7270
## ATTENTION! YOUR WARRANTY IS NOW VOID
Kernel source for Gear S3 devices, optimized for running android platform.  
This source will likely hard brick your device, use the download links or the stable branch below to download stable compiled kernel.
For tizen kernel, use the tizen-kernel branch.

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
## Download links
* LTE version: TBD
* All others: TBD
