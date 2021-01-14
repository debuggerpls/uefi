#### Infos for creating EFI bootable USB

* Create grub image
```
grub-mkimage -o bootx64.efi -p /efi/boot -O x86_64-efi  fat iso9660 part_gpt part_msdos  normal boot linux configfile loopback chain  efifwsetup efi_gop efi_uga  ls search search_label search_fs_uuid search_fs_file  gfxterm gfxterm_background gfxterm_menu test all_video loadenv  exfat ext2 ntfs btrfs hfsplus udf multiboot
```

* Format USB for GPT. (On Ubuntu can use Disks utility)

* Add partition. First partition must be FAT. 

* Mount the USB. Add following folders:
```
<usb-mount>/efi/boot
```

* Copy `bootx64.efi` to `<usb-mount>/efi/boot`

* Create `grub.cfg` in the same folder
