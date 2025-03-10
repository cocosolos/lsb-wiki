**Note: To be able to update the Final Fantasy XI client - and connect to private servers using the most recent version - you must be capable of connecting to retail at least once. Possible methods for doing so may be found below in [Section 2 - Connect to Retail](Client-Setup-Windows#2-connecting-to-retail). LandSandBoat does not condone methods enabling client updates without having connected to SquareEnix's retail servers.**

# 1. Install and Update Final Fantasy XI

1. [Official link to download US installation files](http://www.playonline.com/ff11us/download/media/install_win.html) (get all of them). These files include updates until April 2019.

2. Extract the files first by executing the "FFXIFullSetup_US.part1.exe" then proceed to the installation through "FFXISetup.exe" (freshly extracted).

3. Once the whole installation is complete, execute PlayOnline Viewer. If an update is available, click on "Next", then: 
   * Select "Update" ; once this is done, click on "OK" then "Next". PlayOnline Viewer should restart automatically.
   * Select "For PlayOnline Members!".
   * On the next screen, enter id like 1234ABCD or ABCD1234 (4 letters 4 numbers it doesn't care about the order, doesn't matter if they're accurate or not) in the "Member Name" and "PlayOnline ID"  fields. If you wish to use your retail or trial account, you can input that.
   * Click on "Register" > "Yes" > "OK" > "Exit" and finally "Yes".

4. Check that DirectPlay is enabled.  
This step is for Windows 10 users and can be skipped otherwise.
   * To enable DirectPlay, first press the Windpws key + R keyboard shortcut to open Run.
   * Then enter "Control Panel" in Run, and click the OK button.
   * Click "Programs and Features".
   * Click "Turn Windows features on or off".
   * Double-click "Legacy Components" to expand it.
   * Check the DirectPlay check box (if it is not already marked).

5. Configure game technical optiones.
   * Start Menu > PlayOnline > FINAL FANTASY XI Config; _or_
   * `(Root FFXI Install Directory)/PlayOnline/SquareEnix/FINAL FANTASY XI/Tools/FINAL FANTASY XI Config`

# 2. Connecting to Retail
To be capable of connecting to a private server, you must be able to update your local install of Final Fantasy XI. To do this, you must connect - or have connected - to SquareEnix's retail servers at least once. You may connect to the official retail servers in the following ways:
   1. Connect to retail with your existing retail subscription.
   2. Purchase a copy of Final Fantasy XI, which comes with a 30-day subscription.
   3. For users who have previously purchased Final Fantasy XI and have since reinstalled the software, connect to retail during a Return Home to Vana'diel campaign when SquareEnix allows former subscribers to play on retail servers for free.
   4. [Activate a trial account provided by SquareEnix.](https://store.na.square-enix-games.com/en_US/product/442968/final-fantasy-xi-free-trial-pc-download) When you do so, you will be emailed an activation key. This key may be used like a normal activation key.

# 3. Later Updates

After having connected to retail at least once since installing Final Fantasy XI, you may then update it at any time by deleting a file on your local installation and using "Check Files" from the PlayOnline Viewer. You may use this method even if your previous subscription to retail is inactive.

1. Inside the `\PlayOnline\SquareEnix\FINAL FANTASY XI\ROM\0` folder > delete the `0.dat` file.

2. Execute PlayOnline Viewer. Click on "Check Files" from the list on the left.

3. Select "FINAL FANTASY XI" in the drop-down menu ("PlayOnline Viewer" is selected by default) then click on "Check Files". Be sure that you are checking Final Fantasy XI and not the PlayOnline Viewer.

4. If Final Fantasy XI is not an option available in the drop-down menu from the "Check Files" menu, you have not connected to retail since installing the client.

5. PlayOnline Viewer will find errors, click on "File Repair" then "Yes".

6. Once everything is done, click on "OK" then "Exit Viewer" and "Yes".

# 4. Building xiloader

To connect to a private server, you need to be able to direct _where_ your local client communicates. This is done through programs like [xiloader](https://github.com/zircon-tpl/xiloader/releases).

**Note: Ashita has a loader built into it. Users who plan to use Ashita may skip to [Section 6 - Launcher Configuration](Client-installation-setup-Windows-%28second-part%29/#6-launcher-configuration). However, we _highly recommend_ connecting to your server for the first time with only xiloader so that you can minimize potential setup problems.**

To build xiloader from [source](https://github.com/LandSandBoat/xiloader/):

1. Download and install [MSVC 2015 Runtimes](https://www.microsoft.com/en-ca/download/details.aspx?id=48145) (if needed).

2. Right click wherever you want to download the xiloader repository > Git Clone... > URL: https://github.com/zircon-tpl/xiloader.git > OK > then Close when it's done.

3. Execute Visual Studio Community 2019: Open a project or solution (on the right) > select the "xiloader.sln" file from the \xiloader\ folder > Open (click "OK" when asked to "Retarget Projects").

4. Once it's loaded > Build > Build Solution.

5. To confirm that everything was built properly, you should see:

> ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========

in the output console at the bottom and the xiloader executable file should be present in the \xiloader\Debug\ folder.
Put it wherever you want but remember its path.

# 5. Connecting to a Private Server

* Execute xiloader.exe as an administrator (_after_ launching `xi_connect` and `xi_map` if connecting to your own local sever), then select the "Create New Account" option by hitting "2" then:
```
Username: Username
Password: Password (then repeat)
```
* After that, with each launch, select the "Login" option by hitting "1" then:
```
Username: Username
Password: Password
```

/!\ **Notes** /!\

* Username (3-15) (as displayed on the loader for now): less than 3 characters and more than 15 characters works.
* Password (6-15) (as displayed on the loader for now): less than 6 characters works. More than 15 characters works _when you register, BUT note_ that typing the first 15 characters when you're trying to log in will let you in.

# 6. Launcher Configuration
After confirming that your client can connect to a server, you can use one of the popular third-party launchers for ease-of-use and additional features.

## 6a. Launching via Windower

1. Download [Windower](http://windower.net/).

2. Execute Windower as an administrator and it will download updates automatically.

3. Click on the pen to edit the "Default Profile" and modify its options at your will.

4. Open the settings.xml file and set your options as followed (don't forget to save changes):

```
<profile name="Username">
  <args>--server Server.IP.address --user Username --pass Password</args>
  <executable>HDD:\path\to\xiloader.exe</executable>
</profile>
```

5. Execute Windower.exe.

6. Select your profile and click on the arrow (bottom right), it will launch xiloader.

## 6b. Launching via Ashita

1. Download [Ashita](https://www.ashitaxi.com/).

2. Run Ashita as administrator.

3. Click on the Plus icon to make a new configuration, then edit the file line with the file path to your xiloader (can use the ... to browse).

4. In the command line, place your server details as --server yourserverip --hairpin (if externally facing). You can also use --user and -pass to autopopulate  your credentials.

5. Choose "Window" to adjust your resolution if need be.

6. Click the paper icon to save, launch with the red arrow.
