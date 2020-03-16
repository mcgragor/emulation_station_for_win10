Emulation Station installer and configurator script for Windows 10
======

Auto installer to correctly configure the Emulation Station on a Windows 10 64bit machine.

Highlights
-----

- New themes inserted and automatically configured
- Spaceoddity as a default theme with video support
- Updated the version of Retroarch to the latest
- Uses an updated version of the Emulation Station from the Raspery Pi branch
- Populates emulators with public domain roms automatically
- Automatically installs a popular theme with support for adding favorites
- Initial installer with less than a few KB, since they are just scripts
- Include a roms information retriever inside the rom folder (run% UserProfile% \\. Emulationstation \ roms \ scraper.exe

Translations
------
[Portuguese](README.md)

Steps
------
1. Run powershell_run-as-admin.reg to add "run with administrator" to the power shell scripts in the context menu
2. Run prepare.ps1 in an admin session of Powershell
  (NOTE: Powershell might restart your computer as some libraries require a restart, if so, simply re-run after your PC restarts)
3. Launch Emulation Station and Enjoy
4. Access your ROMS here %UserProfile%\\.emulationstation\roms

Installation GIF:
![alt text](https://github.com/Francommit/github_gif_dump/blob/master/installation-instructions.gif?raw=true)



Troubleshooting
------
- If the controller is not working in game, configure Input in Retroarch (%UserProfile%\\.emulationstation\systems\retroarch\retroarch.exe)
- PSX and PS2 Homebrew Games won't load unless you acquire the bios's and add them to the bios folder (%UserProfile%\\.emulationstation\systems\epsxe\bios and %UserProfile%\\.emulationstation\systems\pcsx2\bios)
- PSX and PS2 also require manual configuration for controllers (%UserProfile%\\.emulationstation\systems\epsxe\ePSXe.exe and %UserProfile%\\.emulationstation\systems\pcsx2\pcsx2.exe)
- If the script fails for whatever reason delete the contents of %UserProfile%\\.emulationstation and try again.
- Emulation Station may crash when you return to it from a external progam, ensure your graphics drivers are up to date.
- Launching a Retroarch rom may return you to ES, you're probably on a 32-bit verison of Windows and need to acquire seperate cores.
- Powershell commands may fail, ensure your Powershell session is in Admin mode.
- If Powershell complains about syntax you're probably somehow running a Powershell version lower than 5. Run 'choco install powershell -y' to update.
- If you are using Xbox controllers and having trouble setting the guide button as hotkey, locate the file (%UserProfile%\\.emulationstation\es_input.cfg and change the line for hotkeyenable to ```<input id="5" name="hotkeyenable" type="button" value="10" />```
- If you are unable to run script from context menu (right mouse button), revert default "Open with" to Notepad

Optional Features and Tips
------
- If you prefer to run your scripts using context menu (right mouse button) but lacks the abilitiy to run they on an admin session, you can just double-click "powershell_run-as-admin.reg" file and accept the registry modification. It creates a new entry on the menu to do that easily.
- If you use OneDrive to store your ROMs and saves, you can run the script onedrive.ps1 or you can modifify it to any other specific folder. Further instructions in comments
- Some new themes shows videos: [es-theme-crt](https://github.com/PRElias/es-theme-crt)
- Script for easy scraping included. Just run and it will backup your gamefile.xml for each ROM folder and produce a new one with data from scrap services (if you have modified your ROM folder, please check before run)

Special Thanks
------
- [jrassa](https://github.com/jrassa/EmulationStation) for his updated version of the Emulation Station build
- [Nesworld](http://www.nesworld.com/) for its free NES ROMs
- [Libretro](https://www.libretro.com/) for your version of Retroarch
- [dtgm](https://chocolatey.org/packages/emulationstation) for maintaining the Emulation Station's chocolatey package
- [OpenEmu](https://github.com/OpenEmu/OpenEmu-Update) for his work on the collection of free rom
- [recalbox](https://github.com/recalbox/recalbox-themes) for their themes
- [Lipebello](https://github.com/lipebello) for the Spaceoddity and Retrorama theme
- [retr0rangepi](https://github.com/retr0rangepi) by the theme Cosmos-ropi
- [RetroPie](https://github.com/RetroPie) for the Carbon theme
- [sselph](https://github.com/sselph/scraper) for his wonderful recovery of information from roms
- [Paulo Elias](http://paulorobertoelias.com.br) for Brazilian Portuguese translation, choco automation and optional features
- [Chris Franco](https://github.com/Francommit) who came up with the idea and put together the entire structure of the original script
