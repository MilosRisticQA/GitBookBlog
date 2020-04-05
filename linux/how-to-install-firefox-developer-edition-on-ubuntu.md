# How to Install Firefox Developer Edition on Ubuntu

To successfully install Mozilla Firefox Developer Edition using terminal in Ubuntu Linux distro do following:

## Steps:

1. Download _Firefox Developer Edition_ from the [_official website_](https://www.mozilla.org/en-US/firefox/developer/)\_\_
2. Open **Terminal**
3. Navigate to **`Downloads`** folder

   ```text
   cd Downloads
   ```

4. Copy **`.tar`** file into **`/opt`** folder

   ```text
   sudo cp -rp firefox-75.0b12.tar.bz2 /opt
   ```

5. Delete the **`.tar`** file 

   ```text
   sudo rm -rf firefox-75.0b12.tar.bz2
   ```

6. Go back to **`home`** directory

   ```text
   cd ~
   ```

7. Navigate into **`/opt`** folder

   ```text
   cd /opt
   ```

8. Un-tar the **`.tar`** file

   ```text
   sudo tar xjf firefox-75.0b12.tar.bz2
   ```

9. Clean up by deleting **`.tar`** file

   ```text
   sudo rm -rf firefox-75.0b12.tar.bz2
   ```

10. Change ownership of the folder containing Firefox Developer Edition **`/opt/firefox`**

    ```text
    sudo chown -R $USER /opt/firefox
    ```

11. Open **`.bashrc`** file

    ```text
    nano ~/.bashrc
    ```

12. Copy and paste this line that _sets the path for the executable file_ 

    ```text
    export PATH=/opt/firefox/firefox:$PATH
    ```

![](../.gitbook/assets/image%20%287%29.png)

Close the file **`Ctrl+X`** , then save by typing **`Y`** , when prompted for file name just click **`Enter`**



