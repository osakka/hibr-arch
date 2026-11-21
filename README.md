# hibr pacman repository

Arch Linux packages of [hibr](https://github.com/osakka/hibr), a small, fast
shell that runs the bash you already write.

## Install

Trust the repository's key, once:

```text
curl -fsSL https://osakka.github.io/hibr-arch/hibr.asc | sudo pacman-key --add -
sudo pacman-key --lsign-key A1E3CA788A8FB02052DA22B413035BE1B1674431
```

then add the repository to `/etc/pacman.conf`:

```text
[hibr]
Server = https://osakka.github.io/hibr-arch/$arch
```

and install:

```text
sudo pacman -Syu hibr
```

`pacman -Syu` keeps it current from then on.

Then `hibr` runs a script, `man hibr` lists every option, and
[From bash to hibr, in ten minutes](https://github.com/osakka/hibr/blob/main/docs/tutorial.md)
is the place to start.

## What there is

| | |
|---|---|
| architectures | x86_64 (aarch64 to follow) |
| installs | `/usr/bin/hibr`, modules in `/usr/lib/hibr`, `man hibr`, and the text desktop (`desktop`) |

The package holds the same files as the Debian package of the same version,
byte for byte, and depends on glibc alone. What a module loads only when it
is first wanted is an optional dependency, listed by `pacman -Si hibr`.

## The signing key

```text
hibr apt repository (signs https://github.com/osakka/hibr-apt) <osakka@gmail.com>
fingerprint A1E3 CA78 8A8F B020 52DA  22B4 1303 5BE1 B167 4431
```

The same key signs the apt, dnf and pacman repositories. Every package and
the database have a detached signature beside them.
