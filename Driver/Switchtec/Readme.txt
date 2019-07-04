----------------------------------------------------------------------------------------------------
Package name:  PCIeSwitch-release_v4.0.0.zip
----------------------------------------------------------------------------------------------------
Version <4.0.0>
Date: <2019/05/31>
RELEASED BY qxie@celestica.com

What Is Included：
1. "switchtec-kernel-release_4.13_to_4.14" for kernel 4.13 to 4.14, 
	the switchtec & ntb_hw_switchtec code base version is v1.1-rc3 from Microsemi github switchtec-kernel；
2. "switchtec-kernel-release_4.19" for kernel 4.19,
	the switchtec & ntb_hw_switchtec code base version is v1.2-rc3 from Microsemi github switchtec-kernel；

New features:
1. Update the code base according to Microsemi’s github.
2. Support automatic loading ntb related drivers. If one canister has built the driver code, then after it rebooting and entering OS again, it will automatic load the NTB & SES related drivers.

Fixed Bugs:
1. Fix the issue that the NTB will lose link after rebooting and reloading ntb related drivers.

User Guide:
1. Run "uname -r" to get the kernel version information;
2. Enter the directory "psx-switchtec-release". 
3. For example, if your kernel version is 4.14.***, you can run "make 4.14". 
   Then the code branch "switchtec-kernel-release_4.13_to_4.14" will be built, the "load_ntb_mod.sh" will be run, so the switchtec related drivers will be loaded.
4. In the script "load_ntb_mod.sh", you can change the eth0 IP address by modifingtwo places in the script:
   (1) ifconfig eth0 192.168.1.100 
   (2) echo -e "BOOTPROTO=static\nIPADDR=192.168.1.100\n..."
   Note: The two places IP addresses in the script should be set the same. 
		 The IP addresses of eth0 of the two canisters in the same chassis need to be set in the same network segment.
5. The script "auto_load_ntb.sh" is used to auto load switchtec related drivers after rebooting.
   This has been set in the Makefile, you don't need to execute this script separately.
6. If your kernel version is 4.14.***, you can run "make 4.14_clean" to clean the built files and unload switchtec and NTB related drivers.
   
Notes: 
1. These scripts are suitable for CentOS7.x system. If you want to use them on other OS versions, you may do some changes.

Changes:
None.

Known Issues:
None.

Repository Information：  (SVN/Git path and commit num/id) 

Dependent Version information:

Install/Upgrade Instruction:


----------------------------------------------------------------------------------------------------


