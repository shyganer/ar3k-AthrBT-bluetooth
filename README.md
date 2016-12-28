# ar3k-AthBT-Bluetooth device

## Useful links
1.http://www.spinics.net/lists/linux-bluetooth/msg62668.html
2.https://bugs.launchpad.net/ubuntu/+source/bluez/+bug/1542743
3.https://bbs.archlinux.org/viewtopic.php?id=201646
4.https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1502781

## Check current system
hwinfo | grep -i bluetooth
rfkill list bluetooth
$> bluetoothctl > list

## Check log
dmesg | grep -i bluetooth
/etc/init.d/bluetooth status
systemctl status bluetooth

## Errors
### (dmesg | grep -i bluetooth)
[    8.556340] Bluetooth: Core ver 2.21
[    8.556356] Bluetooth: HCI device and connection manager initialized
[    8.556359] Bluetooth: HCI socket layer initialized
[    8.556362] Bluetooth: L2CAP socket layer initialized
[    8.556370] Bluetooth: SCO socket layer initialized
[    8.579699] Bluetooth: Patch file not found ar3k/AthrBT_0x00000200.dfu
[    8.579702] Bluetooth: Loading patch file failed
[   38.045796] Bluetooth: BNEP (Ethernet Emulation) ver 1.3
[   38.045801] Bluetooth: BNEP filters: protocol multicast
[   38.045806] Bluetooth: BNEP socket layer initialized


### (hwinfo | grep -i bluetooth)
  E: ID_MODEL_FROM_DATABASE=AR3012 Bluetooth 4.0
  E: ID_MODEL_FROM_DATABASE=AR3012 Bluetooth 4.0
  E: ID_USB_PROTOCOL_FROM_DATABASE=Bluetooth
  E: ID_MODEL_FROM_DATABASE=AR3012 Bluetooth 4.0
  E: ID_USB_PROTOCOL_FROM_DATABASE=Bluetooth
  <6>[   38.045796] Bluetooth: BNEP (Ethernet Emulation) ver 1.3
  <6>[   38.045801] Bluetooth: BNEP filters: protocol multicast
  <6>[   38.045806] Bluetooth: BNEP socket layer initialized
  bluetooth 520192 10 bnep,ath3k,btusb,btrtl,btbcm,btintel, Live 0x0000000000000000
81: USB 00.0: 11500 Bluetooth Device
  Hardware Class: bluetooth
  Model: "Atheros AR3012 Bluetooth 4.0"
  Device: usb 0x3004 "AR3012 Bluetooth 4.0"

## Solution
sudo dpkg -i btusb-lp1542743-dkms_0.1_all.deb 
