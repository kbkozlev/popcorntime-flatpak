# PopcornTime-flatpak
PopcornTime Flatpak package (unoffical)

## TODO:
- [ ] Look for a way to allow external players (maybe add patch to use xdg-open)
- [ ] Setup a basic Gitlab CI Pipeline, which stores the flatpak bundle as an artifact

## Install To System

1 - Install [Flatpak](https://flatpak.org/setup/) & flatpak-builder

2 - Add Flathub remote

```
flatpak remote-add --user --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

3 - Clone the repository

```
git clone https://gitlab.com/Preisschild/popcorntime-flatpak
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
