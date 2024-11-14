This is a simple macOS wrapper application for launching [PlanetarySystemStacker]([url](https://github.com/Rolf-Hempel/PlanetarySystemStacker/tree/master)). 
The macOS application will exectute the `pss.sh` script, which will download any necessary dependencies and launch the PlanetarySystemStacker application.

After downloading the `.zip` file from this repository, place the unzipped directory in your preferred location. You may then place the `PlanetarySystemStackerLauncher.app` file in your `Applications` directory.
To launch the application, double-click on `PlanetarySystemStacker.app`. It is likely that you will see a macOS prompt stating that the application was not opened because macOS could not verify the app is free of malware.
![CleanShot 2024-11-14 at 12 28 31@2x](https://github.com/user-attachments/assets/8f3578a9-f35d-444e-b204-50ac9c6ff1b3)
To resolve this, perform the following steps:
1. Open Settings
2. Navigate to **Privacy & Security**
3. Navigate to the **Security** section (scroll to the bottom of the list)
4. Click **Open Anyway**
   ![CleanShot 2024-11-14 at 12 32 42@2x](https://github.com/user-attachments/assets/6febe05b-a053-430c-8fd3-67ffcdd45738)
5. Click **Open Anyway** in the next prompt
  ![CleanShot 2024-11-14 at 12 33 23@2x](https://github.com/user-attachments/assets/b0129946-1d60-41b6-8465-306240151ebb)
6. Enter your password or perform biometric authentcation if prompted

I included the script in the repository so that you can see what steps occur during the installation and launch procedures.
The script was heavily inspired by this [post](https://www.cloudynights.com/topic/753290-planetarysystemstacker-installation-issues/?p=13545836) from _mdolenga_ in a Cloudy Nights thread.
