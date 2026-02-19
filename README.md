# RedstoneOS
The World's first Linux Minecraft client os based on kde neon


How to Install when booted off of the  flash drive:
Identify the Drives:
Use the lsblk or fdisk -l command to list all available drives and identify the source (the drive you want to clone) and destination (the drive you want to clone to). For example, /dev/sda might be your source and /dev/sdb your destination.
Unmount the Drives:
Ensure that any partitions on the source and destination drives are unmounted. You can unmount a partition using the command:
sudo umount /dev/sdX1
Replace sdX1 with the appropriate partition identifier.
Execute the dd Command:
Run the following command to clone the drive:
sudo dd if=/dev/sda of=/dev/sdb bs=64K conv=noerror,sync
Here, if specifies the input file (source drive), of specifies the output file (destination drive), bs sets the block size (64K is a common choice for speed), and conv=noerror,sync tells dd to continue operation even if it encounters read errors and to pad the output with zeros if there are any read errors. 
Monitor the Progress:
By default, dd does not show progress. To monitor the progress, you can use the pv command in conjunction with dd:
sudo dd if=/dev/sda bs=64K | pv | sudo dd of=/dev/sdb
This will provide a progress bar while cloning. 
Verify the Clone:
After the cloning process is complete, you can verify that the clone was successful by checking the contents of the destination drive or using tools like diff to compare the two drives.
Important Considerations
Data Loss Risk: Be very careful with the dd command, as it can overwrite data on the destination drive. Always double-check the source and destination paths before executing the command.
Drive Size: Ensure that the destination drive is at least as large as the source drive to avoid data loss.
Backup Important Data: Always back up any important data before performing disk cloning operations, as mistakes can lead to data loss. 
Using dd is a powerful method for cloning drives, but it requires caution and attention to detail to avoid potential pitfalls.



Let me know if you want more apps to this image through the Discussions Tab on Github
