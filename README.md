Downloading the Source  
===
1. Repo sync all code with default.xml  
`repo init -u git://github.com/OnePlusOSS/android.git -b oneplus3/6.0.1`  
`repo sync`  
2. Remove vendor/oneplus from your build environment.  
`rm -rf vendor/oneplus` 
3. Clone vendor/oneplus from my Github  
`git clone -b oneplus3-oos321 https://github.com/Naman-Bhalla/vendor_oneplus.git vendor/oneplus` 

Building the System  
===
**[Set up environment]**  
Initialize the environment with the envsetup.sh script.  git a
`$ . build/envsetup.sh`  
**[Choose a Target]**  
Choose which target to build with lunch.  
`$ lunch`  
      enter **25** for msm8996-userdebug  
      enter **26** for msm8996-user  
**[Build the code]**  
Build everything with make. GNU make can handle parallel tasks with a -jN argument.  
`$ make -j4`  
**[Flash a Device]**  
Let device enter fastboot mode, run  
`$ adb reboot bootloader`  
Once the device is in fastboot mode, run  
`$ fastboot flash boot boot.img`  
`$ fastboot flash system system.img`  
If you want flash new /data partition, run  
`$ fastboot flash userdata userdata.img`

