@echo off
echo Scanning for suspicious files...
pause

:: Specify the directories to scan
set directories=C:UsersYourUsernameDownloads C:UsersYourUsernameAppDataLocalTemp

:: Loop through directories and delete suspicious files
for %%d in (%directories%) do (
    echo Scanning %%d...
    del /s /q "%%d*.exe"
    del /s /q "%%d*.vbs"
    del /s /q "%%d*.bat"
)

echo Scan complete.
pause
