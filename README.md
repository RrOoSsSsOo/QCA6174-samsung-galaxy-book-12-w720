# QCA6174-samsung-galaxy-book-12-w720
Set of drivers for Qualcomm Atheros QCA6174 802.11ac Wireless Network Adapter includen into Samsung Galaxy Book 12.0 w720 (https://www.samsung.com/us/support/owners/product/galaxy-book-12-wi-fi)



The `QCA6174.sh` script renames original `board.bin` file and overwrites with the right version. Moreover it deletes the `board-2.bin` file.

Script content:
```
sudo mv /lib/firmware/ath10k/QCA6174/hw3.0/board.bin /lib/firmware/ath10k/QCA6174/hw3.0/board.bin.bak

sudo mv /lib/firmware/ath10k/QCA6174/hw3.0/board-2.bin /lib/firmware/ath10k/QCA6174/hw3.0/board-2.bin.bak

sudo cp ./QCA6174/hw3.0/eeprom_ar6320_3p0_TX8_clpc.bin /lib/firmware/ath10k/QCA6174/hw3.0/board.bin
```

On Manjaro Linux you need to re-launch this script after every update of `linux-firmware` package.

`hwinfo --wlan` comman output:
```
10: PCI 100.0: 0282 WLAN controller                             
  [Created at pci.386]
  Unique ID: yWPJ.ZUPU+4g13N1
  Parent ID: z8Q3.rsg1rcKvXVB
  SysFS ID: /devices/pci0000:00/0000:00:1c.0/0000:01:00.0
  SysFS BusID: 0000:01:00.0
  Hardware Class: network
  Model: "Qualcomm Atheros QCA6174 802.11ac Wireless Network Adapter"
  Vendor: pci 0x168c "Qualcomm Atheros"
  Device: pci 0x003e "QCA6174 802.11ac Wireless Network Adapter"
  SubVendor: pci 0x144d "Samsung Electronics Co Ltd"
  SubDevice: pci 0xc14f 
  Revision: 0x32
  Driver: "ath10k_pci"
  Driver Modules: "ath10k_pci"
  Device File: wlp1s0
  Features: WLAN
  Memory Range: 0xdf400000-0xdf5fffff (rw,non-prefetchable)
  IRQ: 133 (no events)
  HW Address: 00:03:7f:c2:00:43
  Permanent HW Address: 00:03:7f:c2:00:43
  Link detected: yes
  WLAN channels: 1 2 3 4 5 6 7 8 9 10 11 36 40 44 48 52 56 60 64
  WLAN frequencies: 2.412 2.417 2.422 2.427 2.432 2.437 2.442 2.447 2.452 2.457 2.462 5.18 5.2 5.22 5.24 5.26 5.28 5.3 5.32
  WLAN encryption modes: WEP40 WEP104 TKIP CCMP
  WLAN authentication modes: open sharedkey wpa-psk wpa-eap
  Module Alias: "pci:v0000168Cd0000003Esv0000144Dsd0000C14Fbc02sc80i00"
  Config Status: cfg=new, avail=yes, need=no, active=unknown
  Attached to: #3 (PCI bridge)
```
