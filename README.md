# OPEN-SOURCE-EX-7
## Name: Jeffy Brailin T
## Reg.No: 212223040076

## STEPS TO DO :
### STEP 1 : 
sudo pvcreate /dev/sdb
### STEP 2 : 
sudo vgcreate -s 8M vg_backup /dev/sdb
### STEP 3 : 
vgdisplay vg_backup | grep "PE Size"
### STEP 4 : 
PE Size 8.00 MiB
### STEP 5 : 
sudo lvcreate -l 50 -n lv_app_logs vg_backup
### STEP 6 : 
sudo mkfs.ext3 /dev/vg_backup/lv_app_logs
### STEP 7 : 
sudo mkdir /production \n sudo mount /dev/vg_backup/lv_app_logs /production
### STEP 8 : 
df -h /production
### STEP 9 : 
echo "/dev/vg_backup/lv_app_logs /production ext3 defaults 0 0" | sudo tee -a /etc/fstab

## Output:
<img width="424" height="145" alt="image" src="https://github.com/user-attachments/assets/540f12ae-ae1a-4bbe-9ba0-f32a97a4f471" />


## Result:
Thus the code worked correctly in the RedHat Terminal(Lab)

