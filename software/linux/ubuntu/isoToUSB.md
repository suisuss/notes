
### Burn ISO to USB

#### Requirements

- `lsblk`
- `umount`
- `dd`

#### Instructions

- Find the disk you want to burn to. 
    - `lsblk -p | grep "disk"`
- Unmount the disk you want to burn to.
    - `sudo umount [DISK]`
- Use the `dd` program to burn your iso to the disk
    - `sudo dd if=[ISO PATH] of=/dev/[DISK] bs=4M conv=fdatasync status=progress`