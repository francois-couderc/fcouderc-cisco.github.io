# ACI to NXOS switch conversion

Copy NXOS image to bootflash :

```other
Leaf-111# cd bootflash/

Leaf-111# wget http://10.60.7.9/bin/nx-os/n9k/nxos.9.3.8.bin
```

Reload the switch :

```other
Leaf-111# reload
This command will reload the chassis, Proceed (y/n)? [n]: y
```

Interrupt boot process with Ctrl-C :

```other
FPGA SPI Flash MfgId=0x9D, DevId=0x6017, DevSize=0x17

Board type  4
IOFPGA @ 0xd8000000
SLOT_ID @ 0xf
Set fan speed to 60%
Initializing fan controller...
Aborting config file read and autoboot
No autoboot or failed autoboot. falling to loader



                Loader Version 5.44

loader >
```

Set recovery mode and boot on NXOS image :

```other
loader > cmdline recoverymode=1

loader > dir

usb1::
 nxos.9.3.6.bin
 aci-n9000-dk9.15.1.3e.bin

bootflash::
  nxos.9.3.8.bin
  aci-n9000-dk9.14.2.7q.bin

loader > boot nxos.9.3.8.bin

Security Lock
Booting nxos.9.3.8.bin
Trying diskboot
 Filesystem type is ext2fs, partition type 0x83
```

Init NXOS system :

```other
switch(boot)# init system
This command is going to erase your startup-config, licenses as well as the contents of your bootflash:.
Do you want to continue? (y/n)  [n] y
```

Copy NXOS image to bootflash :

```other
switch(boot)# config terminal
Enter configuration commands, one per line.  End with CNTL/Z.
switch(boot)(config)# interface mgmt 0
switch(boot)(config-if)# ip address 192.168.123.112 255.255.255.0
switch(boot)(config-if)# no shut
switch(boot)(config-if)# exit
switch(boot)(config)# ip default-gateway 192.168.123.254
switch(boot)(config)# exit
switch(boot)#
switch(boot)# copy scp://cisco@10.60.7.9/data/bin/nx-os/n9k/nxos.9.3.8.bin bootflash:
The authenticity of host '10.60.7.9 (10.60.7.9)' can't be established.
ECDSA key fingerprint is SHA256:rRPk+rCALpOtPwl0qva1asRlB3seuhj7WKmNIUf8ENk.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '10.60.7.9' (ECDSA) to the list of known hosts.
Outbound-ReKey for 10.60.7.9:22
Inbound-ReKey for 10.60.7.9:22
cisco@10.60.7.9's password:
nxos.9.3.8.bin                                100% 1866MB  25.5MB/s   01:13
Copy complete, now saving to disk (please wait)...
Copy complete.
switch(boot)#
```

Load NXOS :

```other
switch(boot)# load-nxos
```

Reload switch :

```other
bash-4.3# reboot
```

Back in loader mode, force boot on NXOS image :

```o
Loader Version 5.45

loader > dir

usb1::
 nxos.9.3.6.bin
 aci-n9000-dk9.15.1.3e.bin

bootflash::
  nxos.9.3.8.bin

loader > boot nxos.9.3.8.bin
```

