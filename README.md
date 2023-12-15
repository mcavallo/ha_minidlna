## MiniDLNA for hass.io

## Description

This addon provide a container for hass.io with MiniDLNA

## Installation

1. Go to **Settings**, then **Add-ons** and click on **Add-on Store**
2. Open the 3 dots menu, click on **Repositories** and add `https://github.com/mcavallo/ha_minidlna`
3. Refresh your browser
4. Search for `Minidlna`and install it

## Configuration

```yaml
friendly_name: HA Media
media_dir: A,/media
options: -d
```

### Option: `friendly_name`

Set this to specify the name that shows up on your clients.

### Option: `media_dir`

Set this to the directory you want scanned.

- if you want multiple directories, you can add ';' before each new directory
  (eg. media_dir: /media;/share)
- if you want to restrict a media_dir to specific content types, you
  can prepend the types, followed by a comma, to the directory:
  - `A` for audio (eg. media_dir: A,/home/jmaggard/Music)
  - `V` for video (eg. media_dir: V,/home/jmaggard/Videos)
  - `P` for images (eg. media_dir: P,/home/jmaggard/Pictures)
  - `PV` for pictures and video (eg. media_dir:PV,/home/jmaggard/digital_camera)

### Option: `options`

Set this to specify what options are passed to minidlnad.

#### Usage:

```
[-d] [-v] [-f config_file] [-p port]
[-i network_interface] [-u uid_to_run_as]
[-t notify_interval] [-P pid_filename]
[-s serial] [-m model_number]
[-w url] [-r] [-R] [-L] [-S] [-V] [-h]
```

#### Notes:

- `-t` sets the notify interval is in seconds. Default is `895`
- `-P` sets the pid file. Default is `/var/run/minidlna/minidlna.pid`
- `-d` will run minidlna in debug mode (not daemonize)
- `-w` sets the presentation url. Default is http address on port `80`
- `-v` enables verbose output
- `-h` displays this text
- `-r` forces a rescan
- `-R` forces a rebuild
- `-L` do not create playlists
- `-S` changes behaviour for systemd
- `-V` print the version number
