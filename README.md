# Spotify-spice
Installation
Windows
Powershell (pre-built binary) - Recommended
iwr -useb https://raw.githubusercontent.com/spicetify/spicetify-cli/master/install.ps1 | iex

If you have problem with downloading, use this:

iwr -useb https://raw.githubusercontent.com/spicetify/spicetify-cli/master/install_curl.ps1 | iex

Chocolatey
Follow this guide: https://chocolatey.org/packages/spicetify-cli

Scoop
scoop install spicetify-cli

Spotify installed from Scoop
To find the location of your Spotify installation, run scoop prefix spotify.
$ scoop prefix spotify
C:\Users\<username>\scoop\apps\spotify\current

After you have located it, set spotify_path to that directory in Spicetify's config file:

scoop-spotify-path

Winget
winget install Spicetify.Spicetify

Linux and MacOS
Shell (pre-built binary) - Recommended
curl -fsSL https://raw.githubusercontent.com/spicetify/spicetify-cli/master/install.sh | sh

Homebrew or LinuxBrew
brew install spicetify/homebrew-tap/spicetify-cli

AUR
yay -S spicetify-cli

Note for Linux users
Spotify installed from AUR
Before applying Spicetify, you need to gain write permission on Spotify files, by running command:

sudo chmod a+wr /opt/spotify
sudo chmod a+wr /opt/spotify/Apps -R

Note: Your Spotify client location might be different.

Spotify installed from Snap
Apps installed from Snap cannot be modified so you need to follow these steps to get Spicetify working:

Uninstall Spotify in Snap or run command snap remove spotify
Install Spotify using apt:
curl -sS https://download.spotify.com/debian/pubkey_5E3C45D7B312C643.gpg | sudo apt-key add -
echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
sudo apt-get update && sudo apt-get install spotify-client

After Spotify is installed successfully, you need to gain read write permissions on Spotify files, by running commands:
sudo chmod a+wr /usr/share/spotify
sudo chmod a+wr /usr/share/spotify/Apps -R

Note: Your Spotify client location might be different.

Spotify installed from Flatpak
You need to find where Flatpak stores your Spotify client. In Manjaro, it is stored in:
/var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify/

Yours might be different, try these steps:
Find flatpak installation place with command: flatpak --installations
Go to that directory and dig in until you find folder which contain items like these:
flat2

After you have Spotify location, set spotify_path in config file to that directory:

flat2

Find your prefs file: It could be either in these two locations:
~/.config/spotify/prefs
~/.var/app/com.spotify.Client/config/spotify/prefs
Check both, expand the right one to absolute path and set it to prefs_path in config file.

spicetify config prefs_path ~/.var/app/com.spotify.Client/config/spotify/prefs

Finally in terminal, set read/write permission for it:
sudo chmod a+wr /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify
sudo chmod a+wr -R /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify/Apps

Legacy Installations
If, for some reason, you are not using the most up to date Spotify client, you may need to install a specific version of Spicetify. This is not recommended as our prime focus will always be the latest Spotify version.

As such, you will need to run either of the below commands with the desired version. If you wish to use old Spotify client v1.1.56 or older, you have to install spicetify v1.2.1.

Windows: In powershell

$v="1.2.1"; Invoke-WebRequest -UseBasicParsing "https://raw.githubusercontent.com/spicetify/spicetify-cli/master/install.ps1" | Invoke-Expression


Linux/MacOS: In bash

curl -fsSL https://raw.githubusercontent.com/spicetify/spicetify-cli/master/install.sh -o /tmp/install.sh
sh /tmp/install.sh 1.2.1

spicetify v1 code is available in branch legacy if you want to build from source.

If you want legacy themes, you can find them here.
