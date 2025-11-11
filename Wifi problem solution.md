## ✅Wi-Fi: finish the Intel setup



1. **Update system + firmware**
    

`paru -Syu linux-firmware`

(If it offers a kernel update too, accept it.)

2. **Reboot**
    

`sudo reboot`

3. **Bring Wi-Fi up & check devices**
    

`sudo nmcli radio wifi on nmcli dev nmcli dev wifi list`

4. **If still nothing, reload Intel modules**
    

`sudo modprobe -r iwlmvm iwlwifi sudo modprobe iwlwifi sudo nmcli radio wifi on nmcli dev nmcli dev wifi list`

5. **If still missing, get the exact firmware error (use sudo!)**
    

`sudo dmesg | grep -i 'iwl' | tail -n 60`

- If you see a line like: `failed to load firmware iwlwifi-QuZ-a0-hr-b0-*.ucode`, the kernel is telling you the **exact** file it wants. Then:
    
    `paru -Syu            # make sure everything is current # try again after the update/reboot`