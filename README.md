# spotify-adblock-install

**Before installation of package**

**INSTALL BUILDING PACKAGES**
`sudo apt-get install build-essential fakeroot devscripts`

* * *

***INSTALL  RUST WITH THIS COMMANDS***

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

OR GO-TO
https://www.rust-lang.org/tools/install

* * *

***IF YOU DON'T HAVE || INSTALL SPOTIFY CLIENT WITH THIS COMMANDS***

You will first need to configure our debian repository:

`
curl -sS https://download.spotify.com/debian/pubkey_7A3A762FAFD4A51F.gpg | sudo gpg --dearmor --yes -o /etc/apt/trusted.gpg.d/spotify.gpg
echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
`

Then you can install the Spotify client:
`sudo apt-get update && sudo apt-get install spotify-client`

OR GO-TO
https://www.spotify.com/us/download/linux/

* * *

***spotify-adblock***

https://github.com/abba23/spotify-adblock


```
git clone https://github.com/abba23/spotify-adblock.git
cd spotify-adblock
make
```

**INSTALL**
`sudo make install`

  LOOKS LIKE 
![rust.png](rust.png)

You can integrate it with your desktop environment by creating a `.desktop` file (e.g. `spotifyadblock.desktop`) in `~/.local/share/applications`.

```
[Desktop Entry]
Type=Application
Name=Spotify (adblock)
GenericName=Music Player
Icon=spotify-client
TryExec=spotify
Exec=env LD_PRELOAD=/usr/local/lib/spotify-adblock.so spotify %U
Terminal=false
MimeType=x-scheme-handler/spotify;
Categories=Audio;Music;Player;AudioVideo;
StartupWMClass=spotify
```
