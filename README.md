# README

The Xbox iso extractor tool

## Installation

Linux users can use the [installer](https://github.com/timonier/extract-xiso/blob/master/bin/installer):

```sh
curl --location "https://github.com/timonier/extract-xiso/raw/master/bin/installer" | sudo sh -s -- install
```

## Usage

Run the command `extract-xiso`:

```sh
# See all extract-xiso options

extract-xiso -h

# Run extract-xiso

extract-xiso /path/to/xbox.iso
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
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
* [timonier/version-lister](https://github.com/timonier/version-lister)
