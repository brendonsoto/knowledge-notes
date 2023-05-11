## What's an AppImage?
An application!
Like Ubuntu's Snap.
It's an application in a portable format.
Apparently, it's a bit faster to run and slimmer size wise when googling "appImage vs snap vs flatpak"

## How do you use one?
*Assuming it's already downloaded in $HOME/downloads*:
- `chmod a+x <appimage>` -- This is to make it executable

## How can I turn it into a desktop application that I can use like any other application?
- Install the latest release of [AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher/releases)
    - Use the `*x86_64.AppImage` file
- Open your terminal
- `cd ~/Downloads`
- `chmod a+x appimagelauncher-lite-2.2.0-travis995-0f91801-x86_64.AppImage`
- `./appimagelauncher-lite-2.2.0-travis995-0f91801-x86_64.AppImage install`
- Click on the grid that opens the application launcher
- Type in `AppImageLauncher`
- Click the app
- Double check settings
- Open any other AppImage app
- You should get a notification to move the app
If that doesn't work:
- Move the AppImage you're trying to use to `~/Applications` (or where ever you set the download location to be in `AppImageLauncher`)
- Open the app
- Close the app
- Click on the grid that opens the application launcher
- Type in the name of the app you're trying to install
- The app should be there now