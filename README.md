## category

Files/Directorys categorization tool.

### Install

    npm i category -g

### Usage

```
$ category -h

  Usage: category <src> <des>

  Files/Directorys categorization tool.

  Options:

    -h, --help             output usage information
    -V, --version          output the version number
    -i, --input [regexp]   regexp of file to category (required)
    -o, --output [regexp]  regexp of dir to generate (required)
    -f, --force            whether to delete original file

  Example:

    $ category -i "^IMG_(\d{4})(\d{2})(\d{2})_\d{6}(\.jpg)?$" -o "$1-$2-$3" -f ./test ./test


```

### Example

```
$ category -i "^IMG_(\d{4})(\d{2})(\d{2})_\d{6}(\.jpg)?$" -o "$1-$2-$3" -f ./test ./test
```

before:

```
test/
├── IMG_20150425_133502.jpg
├── IMG_20150426_134524.jpg
├── IMG_20150427_123602.jpg
├── IMG_20150427_221603.jpg
└── IMG_20150427_221604/
```

after:

```
test/
├── 2015-04-25/
│   └── IMG_20150425_133502.jpg
├── 2015-04-26/
│   └── IMG_20150426_134524.jpg
└── 2015-04-27/
    ├── IMG_20150427_123602.jpg
    ├── IMG_20150427_221603.jpg
    └── IMG_20150427_221604/ 
```

### Personal usage

```
category -i '^(IMG|VID)_(\d{4})(\d{2})(\d{2})_\d{6}(\.(jpg|mp4))?$' -o '$2—$3—$4' -f ./Camera ./Camera
```

### Test

    npm test

### License

MIT