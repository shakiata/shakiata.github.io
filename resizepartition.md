1) Resizing a partition in a lvm


lsblk
sudo parted /dev/sda
   print
   resizepart 3
   100%
   quit
lsblk
df -h
sudo pvresize /dev/sda3
sudo pvdisplay /dev/sda3
sudo lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
sudo resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv

df -h

