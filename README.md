# Add Printers to Kali Linux (Debian Based distro)

> [!NOTE]
> Execute as normal user.
> All drivers for HP and Canon Printers

1. Install CUPS and Foomatic Databases where the drivers are stored
   ```
   sudo apt install cups cups-client foomatic-db
   ```

2. Verify if your current user is in `lpadmin` group
   ```
   groups <username>
   ```
   It will show all groups where the user is member of.
   > If you don't see `lpadmin` in the list then add the user to group: `sudo usermod -aG lpadmin <user>`
   > Then, check again

3. Enable CUPS (allowing it to start at boot)
   ```
   sudo systemctl enable --now cups
   ```

4. You can now access to CUPS Web Interface by opening [http://127.0.0.1:631](http://127.0.0.1:631) in a web browser.

5. Follow these steps once UI:
   - CUPS for Administrators
   - Adding Printers and Classes
   - Administration
   - Enter you system username and password (The one you used to log in to your PC and you recently added to group `lpadmin`)
   - Add Printer
   - On Discovered Network Printers, you should see your printer if you are connected on the same network.
     Choose Local Printers if you are connected to printer using Serial Port
     Or add it manually using Other Network Printers
   - Rename it if necessary and Set Location (eg. Home). Don't tick Sharing if don't want to share the printer using your PC (Others users on the network can still use it) and click on Continue.
   - Select the appropriate Model (if you are not sure, select one with `recommended` option) and click on Add Printer
   - You should now use your printer to print Documents, Photo, ...


### Credit dijey099
