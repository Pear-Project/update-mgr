# Update Manager for pearOS
Update manager. It checks for updates everytime the system is booted.
It uses an update server

## Dependencies

   - install gambas3 package
   ```sh
   $ sudo apt-get install gambas3 -y
   ```

## Installation steps
 - From Source:

   - clone the project
   ```sh
   git clone https://github.com/alxb421/update-mgr.git
   ```
   - Open gambas3 application (from terminal `$ gambas3`, or from application dashboard, search for gambas3)
   - Click `Open`
   - Navigate to cloned folder, and open the project
   - Click on `Project` > `Make` > `executable`
   - copy the new executable in the `/usr/bin` folder of your Linux machine
   ```sh
   $ sudo cp <path to your previously built update-mgr.gambas> /usr/bin/update-mgr
   ```
   - copy `xyz.pearos.update-manager.desktop` from the cloned repository to the autostart folder
   ```sh
   $ cp -r ~/update-mgr/xyz.pearos.update-manager.desktop ~/.config/autostart
   # this was an example for adding autostart script to KDE based system
   ```
   - move `update` file to `/usr/bin` and make it executable
   ```sh
   sudo cp ~/update-mgr/update /usr/bin
   sudo chmod +x /usr/bin/update
   ```
   - Enjoy :p

 - From Package:
   - Download the .deb package from `Releases` tab here, in GitHub
   - Install using gdebi/ dpkg
   ```sh
   $ sudo dpkg -i <path to downloaded deb file, or drag and drop>
   ```
   - clone the project
   ```sh
   git clone https://github.com/alxb421/Control-Centre.git
   ```
   - copy `xyz.pearos.update-manager.desktop` from the cloned repository to the autostart folder
   ```sh
   $ cp -r ~/update-mgr/xyz.pearos.update-manager.desktop ~/.config/autostart
   # this was an example for adding autostart script to KDE based system
   ```
   - move `update` file to `/usr/bin` and make it executable
   ```sh
   sudo cp ~/update-mgr/update /usr/bin
   sudo chmod +x /usr/bin/update
   ```
   
   ## Usage
   Check for updates using `update-mgr` in terminal
   See current installed update version by running `update -v` or `update --version`
   See installed update changelog by running `update -c` or `update --changelog`
   See more command by running `update -h` or `update --help`
   
   If there is an update available, after running `update-mgr`, it will open the PEXT-INSTALLER and send a notification to the user.
   If there is no update available, it exits or returne `segmentation fault`.
