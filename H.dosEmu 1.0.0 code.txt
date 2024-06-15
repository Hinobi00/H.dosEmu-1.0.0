@echo off
cd ..
cd ..
cd ..
:reboot
title H.dosEmu:BIOS
set newcd=\
cls
echo HINOBI
echo Starting...
timeout 3 >nul
cls
color 1F
echo HINOBI
echo Welcome,chose your BOOT
echo 1. H.dos 1.0
echo 2. CD
echo emu. CMD
echo.
set /p boot=BOOT:
color 07
if %boot%==1 goto h.dos
if %boot%==2 goto DVD
if %boot%==emu goto cmd
goto reboot
:h.dos
if %boot%==1 goto 1.0
:1.0
cls
title H.dosEmu:H.dos 1.0
echo Starting h.dos...
timeout 10 > nul
cls
echo Hinobi H.dos 1.0
goto com
:com
set com=none
echo.
set /p com=C:%newcd%:
if %com%==none goto com
if %com%==cd goto cd
if %com%==shutdown goto shutdown
if %com%==reboot goto reboot
:cd
set /p newcd=Fichier
goto com
:DVD
title H.dosEmu:BOOT:DVD
cls
echo DVD
echo 1. H.dos 1.0 install
set /p bootdvd=BOOT dvd
if %bootdvd%==1 goto h.dos1.0install
:h.dos1.0install
cls
echo installed:H.dos 1.0.exe
echo installed
pause
goto reboot
:cmd
title H.dosEmu:CMD
cls
cmd
goto reboot
:shutdown
cls
pause>nul
goto reboot