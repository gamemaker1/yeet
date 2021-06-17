# YEET

Yet another minimal [pacman](https://wiki.archlinux.org/title/Pacman) wrapper. Yeet!

Inspired by several AMAZING projects: [`pacaur`](https://aur.archlinux.org/pacaur), [`pikaur`](https://aur.archlinux.org/pikaur), [`yay`](https://aur.archlinux.org/yay) and [`paru`](https://aur.archlinux.org/paru). Uses [`package-query`](https://aur.archlinux.org/package-query) to query packages from the sync repos and AUR.

## Preview

![[Yeet installing package-query](./assets/media/install-process.png)](./assets/media/install-process.png)

[Yeet installing package-query]

More images [here](./assets/media/).

## Installation

### AUR

If you already have an [AUR helper/pacman wrapper](https://wiki.archlinux.org/title/AUR_helpers) installed, you can install `yeet` from [AUR](https://aur/archlinux.org/packages/yeet).

### Install script

The script will perform the steps given in the [Manual Installation section](#manual) for you. Run the following in your terminal:

Using `cURL`:

```
curl https://raw.githubusercontent.com/gamemaker1/yeet/develop/assets/package/install | bash
```

Using `wget`:

```
wget https://raw.githubusercontent.com/gamemaker1/yeet/develop/assets/package/install -O - | bash
```

### Manual

Requires:

- [git](https://aur.archlinux.org/git) [`pacman -S git`]
- [base-devel](https://aur.archlinux.org/base-devel) [`pacman -S base-devel`]

Clone the AUR package and build yeet:

```
mkdir -p ~/.cache/yeet/build/
cd ~/.cache/yeet/build/
git clone https://aur.archlinux.org/yeet.git
cd yeet
makepkg -sfcCi
```

## Usage

`yeet` aims to be a minimal AUR helper/pacman wrapper. Yeet:

- can search for a package; and then install it (`yeet <package search terms>`)
- can install a package from AUR or the official repos (`yeet -S <package-name>`)
- allows you to edit build files before installing an AUR package (default file manager is `ranger`; this can be changed)
- can build an AUR package using its PKGBUILD (`yeet -B <path to package dir>`)
- can remove a package and any unneeded dependencies (`yeet -R <package-name>`)
- can upgrade all packages (`yeet -U`)
- allows you to run common `pacman` operations (`yeet -<D/F/Q/T> [more pacman-specific options]`)
- can be configured easily - either through environment variables; or the config file, located at `$XDG_CONFIG_HOME/yeet/yeet.conf` OR `$HOME/.config/yeet/yeet.conf`. An example configuration can be found on your machine at `/usr/share/yeet/yeet.conf` or [here](./assets/package/yeet.example.conf).

## Contributing

Thank you for your interest in contributing to `yeet`!

You can contribute to `yeet` by spreading the word, spotting and fixing bugs, and help adding new features. `yeet` is just a bash script, you may edit [the file](./source/yeet) and submit a pull request. Suggestions and PRs welcome!

## License

### GNU GPL v3

Copyright (C) 2021 Vedant K (gamemaker1) \<gamemaker0042 at gmail dot com\>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <https://www.gnu.org/licenses/>.
