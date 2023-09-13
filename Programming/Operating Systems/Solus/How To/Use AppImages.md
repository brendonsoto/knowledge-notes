## What's an AppImage?
An application!
Like Ubuntu's Snap.
It's an application in a portable format.
Apparently, it's a bit faster to run and slimmer size wise when googling "appImage vs snap vs flatpak"

## How do you use one?
*Assuming it's already downloaded in $HOME/downloads*:
- `chmod a+x <appimage>` -- This is to make it executable

## How can I turn it into a desktop application that I can use like any other application?
### DIY
- Move the file to a place on your `$PATH` (e.g. I have `~/.local/bin`)
- Download an image to use as for the app's desktop icon
- Make a file similar to what's below, replacing the template content:
    - For what categories to use, see [here](https://specifications.freedesktop.org/menu-spec/latest/apa.html)

```
[Desktop Entry]
Name=<App-Name>
Exec=<Path-to-the-executable>
Icon=<Path-to-the-icon>
Comment=<Whatcha want to say?>
Type=Application
Terminal=false
Encoding=UTF-8
Categories=<Category1;Category2;>
```

- Set the file's permissions to 644 (owner can read/write, group read, and others read)
- Move the `.desktop` file to `/usr/share/applications/`


### With AppImageLauncher
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
