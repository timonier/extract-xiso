# README

## Installation

Copy the file `bin/extract-xiso` into your executable folder (like `/usr/local/bin` or `$HOME/bin`):

```sh
sudo curl -sLo /usr/local/bin/extract-xiso "https://github.com/timonier/extract-xiso/raw/master/bin/extract-xiso"
sudo chmod +x /usr/local/bin/extract-xiso
```

Linux users can use the [installer](https://github.com/timonier/extract-xiso/blob/master/bin/installer):

```sh
curl -sL "https://github.com/timonier/extract-xiso/raw/master/bin/installer" | sudo sh -s install
```

## Usage

Run the command `extract-xiso`:

```sh
extract-xiso /path/to/xbox.iso
```

__Note__: By default, the version `2.7.1` will be used. To change the version, define the `TAG` before the command:

```sh
extract-xiso -v
# extract-xiso v2.7.1 (01.11.14) for linux - written by in <in@fishtank.com>

TAG="..." extract-xiso -v
# ...
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [extract-xiso](https://sourceforge.net/projects/extract-xiso/)
* [image "timonier/extract-xiso"](https://hub.docker.com/r/timonier/extract-xiso/)
