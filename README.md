# PopcornTime-flatpak
PopcornTime Flatpak package (unoffical) version: 0.51 with freedesktop 24.08
cloned from https://gitlab.com/Preisschild/popcorntime-flatpak

## Install To System

1 - Install [Flatpak](https://flatpak.org/setup/) & flatpak-builder

2 - Add Flathub remote

```
flatpak remote-add --user --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

3 - Clone the repository

```
git clone https://github.com/fastrizwaan/popcorntime-flatpak.git
cd ./popcorntime-flatpak
``` 


4 - Put Popcorn-Time in a local flatpak repository
```
flatpak-builder --user --repo=repo --install-deps-from=flathub --force-clean build-dir org.popcorntime.PopcornTime.json
```

5 - Install Popcorn-Time
```
flatpak --user remote-add --no-gpg-verify popcorn-time-repo repo
flatpak --user install popcorn-time-repo org.popcorntime.PopcornTime
```

6 - Create flatpak-bundle (.flatpak file)
```
flatpak build-bundle ~/.local/share/flatpak/repo org.popcorntime.PopcornTime.flatpak org.popcorntime.PopcornTime
```
