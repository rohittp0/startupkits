# 5. Basic Setup Instructions

------------
####`ATTENTION!!!`
```warning
- Proceed step by step and Complete all Steps.
```
This section guides to review the files received from quectel and download additional software tools required.

__5.1 Identify Resources__ ___(Quectel)___
   
   1. Software Development Kit(SDK)
      - SDK contains the cross compiler and it has the complete source code instruction to be executed in the build.
      - File Name: `EC25EFAR06A01M4G_OCPU_01.001.01.001_SDK.tar.bz2`
   2. Quectel base binaries
      - Pre-built images/binaries required for EC25, will be used in Recovery.
      - File Name: `EC25EFAR06A01M4G_OCPU_01.001.01.001.zip`
   3. QFlash Tool
      - Tool which runs in Windows machine and used to flash the prebuilt images for first time or at recovery using emergency download mode(EDL) 
      - File Name: `QFlash_V5.2_EN.zip` 
   4. USB Driver
      - USB driver for EC25
      - File Name: `Quectel_LTE_5G_Windows_USB_Driver_V2.1.zip`

------------

__5.2 Download Supporting Scripts__
  - Download the load.bat from <a href="https://mirrors.edge.kernel.org/caf_patches/external/startupkit/ec25/EC25-Relv1.2/load.bat" target="_blank">https://mirrors.edge.kernel.org/caf_patches/external/startupkit/ec25/EC25-Relv1.2/load.bat</a>
    - Use `Save As` option to save as `load.bat`
    - `load.bat` script contains fastboot commands to flash different binaries.

__5.3 Download Debugging Tools__ 
  - Download ADB drivers from <a href="https://adb.clockworkmod.com/" target="_blank"> adb.clockworkmod.com </a>
    - <a href="https://github.com/koush/adb.clockworkmod.com/releases/latest/download/UniversalAdbDriverSetup.msi" target="_blank">https://github.com/koush/adb.clockworkmod.com/releases/latest/download/UniversalAdbDriverSetup.msi </a>
  - Download Platformtools version 29.0.6 from <a href="https://androidsdkmanager.azurewebsites.net/Platformtools" target="_blank"> https://androidsdkmanager.azurewebsites.net/   Platformtools </a>
    - <a href="https://dl.google.com/android/repository/platform-tools_r29.0.6-windows.zip" target="_blank">https://dl.google.com/android/repository/platform-tools_r29.0.6-windows.zip</a>
  - Download  <a href="https://mobaxterm.mobatek.net/download-home-edition.html" target="_blank">https://mobaxterm.mobatek.net/download-home-edition.html</a>
    - <a href="https://download.mobatek.net/2012020021813110/MobaXterm_Installer_v20.1.zip" target="_blank">https://download.mobatek.net/2012020021813110/MobaXterm_Installer_v20.1.zip</a>
  - Download Serial Monitor like Tera-Term application <a href="https://osdn.net/projects/ttssh2/downloads/72009/teraterm-4.105.exe/" target="_blank">Tera Term</a>

__5.4 Create the EC25 folder struture in windows command prompt__

 ```console
 mkdir C:\EC25\SW\Apps\ C:\EC25\SW\Built_Images\ C:\EC25\Tools
 ```

![N|Solid](../pics/EC25/ec25-cmd.jpg)

__5.5 Setup EC25 folder struture__

   1. Copy the Downloaded files to EC25 folder struture. 
    - Copy `EC25EFAR06A01M4G_OCPU_01.001.01.001_SDK.tar.bz2` to `C:\EC25\SW\`
    - Copy `EC25EFAR06A01M4G_OCPU_01.001.01.001.zip` to `C:\EC25\SW\`
    - Copy `ec25-qdn_relv0.1.zip` to `C:\EC25\SW\`
    - Copy `load.bat` to `C:\EC25\SW\Built_Images\`
    - Copy `QFlash_V5.2_EN.zip` to `C:\EC25\Tools\`
    - Copy `Quectel_LTE_5G_Windows_USB_Driver_V2.1.zip` to `C:\EC25\Tools\`
    - Copy `platform-tools_r29.0.6-windows.zip` to `C:\EC25\Tools\`
    - Copy `UniversalAdbDriverSetup.exe` to `C:\EC25\Tools\`
    - Copy `MobaXterm_installer_20.1.zip` to `C:\EC25\Tools\`
    - Copy `teraterm-4.105.exe` to `C:\EC25\Tools\`

   2. Compare and verify the contents of `EC25`<br>

    📦EC25<br>
    ┣ 📂SW<br>
    ┃ ┣ 📂Apps<br>
    ┃ ┣ 📂Built&#95;Images<br>
    ┃ ┃ ┗ 📜load.bat<br>
    ┃ ┣ 📜EC25EFAR06A01M4G&#95;OCPU&#95;01.001.01.001&#95;SDK.tar.bz2<br>
    ┃ ┣ 📜EC25EFAR06A01M4G&#95;OCPU&#95;01.001.01.001.zip<br>
    ┃ ┗ 📜ec25-qdn&#95;relv1.0.zip<br>
    ┗ 📂Tools<br>
    ┃ ┣ 📜QFlash&#95;V5.2&#95;EN.zip<br>
    ┃ ┣ 📜platform-tools&#95;r29.0.6-windows.zip<br>
    ┃ ┣ 📜UniversalAdbDriverSetup.exe<br>
    ┃ ┣ 📜MobaXterm&#95;installer&#95;20.1.zip<br>
    ┃ ┣ 📜teraterm-4.105.exe<br>
    ┃ ┗ 📜Quectel&#95;LTE&#95;5G&#95;Windows&#95;USB&#95;Driver&#95;V2.1<br>

__5.6 Setup QFlash Tool__
- Extract `C:\EC25\Tools\QFlash_V5.2_EN.zip` to `C:\EC25\Tools\QFlash_V5.2_EN` and verify the installation
    - `C:\EC25\Tools\QFlash_V5.2.exe`


__5.7 Setup USB Driver & Serial Terminal__
- Install the USB Driver and verify the installation
    - `C:\EC25\Tools\Quectel_LTE&5G_Windows_USB_Driver_V2.1\setup.exe `
- Install the Tera-Term application and verify the installation
    - `C:\EC25\Tools\teraterm-4.105.exe `

__5.8 Setup Debugger Tools__
- Extract `C:\EC25\Tools\platform-tools_r29.0.6-windows.zip` to `C:\EC25\Tools\platform-tools` and verify the installation
    - `C:\EC25\Tools\platform-tools\adb.exe`
    - `C:\EC25\Tools\platform-tools\fastboot.exe`
    - Add above path to adb & fastboot location to __System Path__.
        - `Instructions`: <a href="https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/" target="_blank">www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/</a>
- Install the ADB drivers for EC25.
    - Install the `C:\EC25\Tools\UniversalAdbDriverSetup.exe`
- Extract `C:\EC25\Tools\MobaXterm_Installer_v20.1.zip` to `C:\SC66\Tools\MobaXterm_Installer_v20.1` Use default options to install
    - `C:\EC25\Tools\MobaXterm_Installer_v20.1\MobaXterm_Installer_v20.1.exe`
- Alternative ADB driver Instructions Videos
    - <a href="https://youtu.be/gOT2JlqNjuA" target="_blank">https://youtu.be/gOT2JlqNjuA</a>
    - <a href="https://youtu.be/WVIzOsQBLRc?t=75" target="_blank">https://youtu.be/WVIzOsQBLRc?t=75</a>
  

------------