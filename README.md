# Update Vendor Blobs
A guide on how to update your vendor tree blobs from stock ROM

# Android Vendor Trees
- Vendor Blobs are purely based on proprietary-list.txt included in the device tree used in extracting.
- It maybe edited or not edited.
- Device and vendor names might different from what the device itself says.
    - So I will be putting the device name in the description area just to be clear.

## Credits:
- [Dumpyara](https://github.com/sebaubuntu-python/dumpyara)
- [Aospdtgen](https://github.com/sebaubuntu-python/aospdtgen)
- [DumprX](https://github.com/DumprX/DumprX)
- [AndroidDump](https://github.com/AndroidDumps/dumpyara)
- LineageOS
    - [Extract-Tools](https://github.com/LineageOS/android_prebuilts_extract-tools)
    - [Extract-Utils](https://github.com/LineageOS/android_tools_extract-utils)
    
## Guide to update vendor blobs from Android dump
- Dump a Firmware using dumping tool/script of your choice like Dumpyara, DumprX..etc.
- Change directory to the rom source
- Clone neccessary tools/scripts inside the rom source directory - most lineage based roms have these two repos cloned already:
```
     git clone https://github.com/LineageOS/android_tools_extract-utils -b lineage-22.2 android/tools/extract-utils
     git clone https://github.com/LineageOS/android_prebuilts_extract-tools -b lineage-22.2 android/prebuilts/extract-tools
```
 - Clone or Copy/Move your Existing Device Tree inside device/vendorname/codename directory if not already cloned.
    - If you don't have yet, use aosptdtgen to generate device tree.
### For .sh script 
 - Directory should be look like this: for sh script 
 ```
    - rom_source/
        - device/
            - vendorname/
                - devicecodename/
        - android/
            - tools/
                - extract-utils/
            - prebuilts/
                - extract-tools/
  ```
  - Inside you device tree folder, run:
  ```
  ./extract-files.sh /path/directory/to/your/rom_dump/
  ```
### For .py script 
  - same structure as above of path 
  - if you use paython script then do this:
  - define tool path PYTHONPATH=../../../tools/extract-utils
  ```
  chmod a+x extract-files.py
  ./extract-files.sh /home/mayuru02/d/out
  ```


- Wait until finished. You'll find the blobs under android/vendor/vendorname/codename   
