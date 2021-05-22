The start of this is borrowed from (https://github.com/AEFeinstein/Super-2021-Swadge-FW-Sandbox/blob/master/docs/GETTING_STARTED.md).

## Getting a Linux Environment
This is compiled under the Windows Subsystem for Linux.
1. Install Windows Subsystem for Linux (WSL) by following this guide: (https://docs.microsoft.com/en-us/windows/wsl/install-win10)
2. Install Ubuntu 20.04 LTS from the Microsoft Store: (https://www.microsoft.com/en-us/p/ubuntu-2004-lts/9n6svws3rx71)
3. Initialize Ubuntu 20.04 LTS by following the guide here, and DO NOT UPDATE TO WSL2: (https://docs.microsoft.com/en-us/windows/wsl/initialize-distro)

The reason you don't want to upgrade to WSL2 is because they don't have USB COM port integration.  You can read up on that here: (https://docs.microsoft.com/en-us/windows/wsl/wsl2-faq).  If you are using WSL2, you can in theory use this protocol anyways: (https://matevarga.github.io/esp32/m5stack/esp-idf/wsl2/2020/05/31/flashing-esp32-under-wsl2.html)

It's relatively easy to switch between WSL1 and WSL2.  You can find instructions here: (https://winaero.com/set-linux-distro-version-to-wsl-1-or-wsl-2-in-windows-10)

## Compiling the Firmware
Follow the Linux Entries in the following Steps:  (https://docs.espressif.com/projects/esp-idf/en/latest/esp32c3/get-started/index.html#step-1-install-prerequisites)

For **Step 6. Connect Your Device** WSL1 automatically maps Windows COM ports.  For example, COM3 gets mapped to /dev/ttyS3
After plugging in the USB Cable, use Device Manager and verify under Ports (COM & LPT) you have an entry that says "Silicon Labs CP210x USB to UART Bridge (COM<X>)

For **Step 7. Configure** there is nothing to configure for either the *hello_world* or *blink* example.  In menuconfig, just [S]ave and [Q]uit.

For **Step 9. Flash onto the Device** You'll need to lower the BAUD rate from the default of 460,800.  I found that 19,200 to 230,400 worked.  (Note: the CP210x supports up to 3Mbps and the ESP32-C3 supports up to 5Mbps.  So it's a bit unclear why you need to set such a slow BAUD rate.)
In my system, the board identified as COM3, and the following command worked:  **idf.py -p /dev/ttyS3 flash -b 230400**
  
Espressif supports VS Code integration.  You can read up on how you develop linking VS Code and WSL here: (https://code.visualstudio.com/docs/remote/wsl)  You can read up on Espressif's VS Code integration here: (https://github.com/espressif/vscode-esp-idf-extension).  There is a nice video here: (https://www.youtube.com/watch?v=Lc6ausiKvQM)  I was not able to figure out how to Flash from VS Code.
Once you have installed VS Code, just run the following command in the top level directory of your project: **code .**
