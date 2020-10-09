# README

The Xbox iso extractor tool

If you like / use this project, please let me known by adding a ★ on the [GitHub repository](https://github.com/timonier/extract-xiso).

## Installation

```sh
# Define installation folder

export INSTALL_DIRECTORY=/usr/bin

# Use local installation

sudo bin/installer install

# Use remote installation

curl --location "https://github.com/timonier/extract-xiso/raw/master/bin/installer" | sudo sh -s -- install
```

__Note 1__: If you do not define `INSTALL_DIRECTORY`, `installer` will use in `/usr/local/bin`.

__Note 2__: `docker-for-mac` users have to configure [native NFS server](https://medium.com/@sean.handley/how-to-set-up-docker-for-mac-with-native-nfs-145151458adc).

## Usage

Run the command `extract-xiso`:

```sh
# See all extract-xiso options

extract-xiso -h

# Run extract-xiso

extract-xiso /path/to/xbox.iso
```

## Links

* [extract-xiso](https://sourceforge.net/projects/extract-xiso/)
* [image "timonier/extract-xiso"](https://hub.docker.com/r/timonier/extract-xiso/)
* [set up docker for mac with native nfs](https://medium.com/@sean.handley/how-to-set-up-docker-for-mac-with-native-nfs-145151458adc)
* [timonier/extract-xiso](https://github.com/timonier/extract-xiso)
