A file system is used to keep track of files and file storage on a disk. ​OS cannot organizefiles without this system. Windows use **NTFS** File system.
A USB drive that is using NTFS file system can be read by both windows and linux but if the USB use ext4` linux file system it can only be read by linux not windows. So USB comes with FAT32 file system that can be read by windows, linux and Mac OS. 
# Disk Partitions and and Formating File System
**A disk** is a storage device used to store data permanently. For examples, SSD (Solid State Drive), HDD (Hard Disk Drive) ,USB and Virtual Disk in a Virtual Machine.
**Disk partitioning** is the process of dividing a storage device into separate sections called partitions. Each partition can contain its own file system and can be used for different purposes such as operating system files, user data, recovery tools, or swap space.
### MBR and GPT Partition Styles
Before a disk can store partitions it needs a partitioning scheme. ​A partition table tells ​the OS how the disc is partitioned. ​The table will tell you which ​partitions you can boot from, ​how much space is allocated to partition, etc. ​There are two main partition table schemes that are used .The two common partition tables are:

* MBR (Master Boot Record)
* GPT (GUID Partition Table)

These define how partition information is stored on a disk.

### MBR vs GPT

| Feature           | MBR                        | GPT                  |
| ----------------- | -------------------------- | -------------------- |
| Full Name         | Master Boot Record         | GUID Partition Table |
| System Type       | Older BIOS systems         | Modern UEFI systems  |
| Maximum Disk Size | 2 TB                       | More than 2 TB       |
| Partitions        | Up to 4 primary partitions | 128 partitions      |
| Reliability       | Lower                      | Higher               |
| Modern Use        | Legacy systems             | Current systems      |
