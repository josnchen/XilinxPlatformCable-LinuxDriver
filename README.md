This is a linux driver for Xilinx Platform Cable.

The master branch is cloned from: git://git.zerfleddert.de/usb-driver

dependency: libusb-dev  fxload

Usage:
1. Compile: make
2. export LD_PRELOAD=/yourpath/libusb-driver.so
3. sudo ./setup_pcusb /yourpath/12.4/ISE_DS/ISE  
   or add mannualy:
   https://github.com/timvideos/HDMI2USB/wiki/Xilinx-Platform-Cable-USB-under-Linux
  /etc/udev/rules.d/xusbdfwu.rules
  ```
  # version 0003
  ATTRS{idVendor}=="03fd", ATTRS{idProduct}=="0008", MODE="666"
  SUBSYSTEM=="usb", ACTION=="add", ATTRS{idVendor}=="03fd", ATTRS{idProduct}=="0007", RUN+="/sbin/fxload -v -t fx2 -I /opt/Xilinx/14.7/ISE_DS/ISE/bin/lin64/xusbdfwu.hex -D $tempnode"
  SUBSYSTEM=="usb", ACTION=="add", ATTRS{idVendor}=="03fd", ATTRS{idProduct}=="0009", RUN+="/sbin/fxload -v -t fx2 -I /opt/Xilinx/14.7/ISE_DS/ISE/bin/lin64/xusb_xup.hex -D $tempnode"
  SUBSYSTEM=="usb", ACTION=="add", ATTRS{idVendor}=="03fd", ATTRS{idProduct}=="000d", RUN+="/sbin/fxload -v -t fx2 -I /opt/Xilinx/14.7/ISE_DS/ISE/bin/lin64/xusb_emb.hex -D $tempnode"
  SUBSYSTEM=="usb", ACTION=="add", ATTRS{idVendor}=="03fd", ATTRS{idProduct}=="000f", RUN+="/sbin/fxload -v -t fx2 -I /opt/Xilinx/14.7/ISE_DS/ISE/bin/lin64/xusb_xlp.hex -D $tempnode"
  SUBSYSTEM=="usb", ACTION=="add", ATTRS{idVendor}=="03fd", ATTRS{idProduct}=="0013", RUN+="/sbin/fxload -v -t fx2 -I /opt/Xilinx/14.7/ISE_DS/ISE/bin/lin64/xusb_xp2.hex -D $tempnode"
  SUBSYSTEM=="usb", ACTION=="add", ATTRS{idVendor}=="03fd", ATTRS{idProduct}=="0015", RUN+="/sbin/fxload -v -t fx2 -I /opt/Xilinx/14.7/ISE_DS/ISE/bin/lin64/xusb_xse.hex -D $tempnode"
  ```
  Run: `sudo udevadm control --reload-rules`

  see more in README
