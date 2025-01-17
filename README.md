# hexo-fs

[![Build Status](https://github.com/hexojs/hexo-fs/workflows/Tester/badge.svg)](https://github.com/hexojs/hexo-fs/actions?query=workflow%3ATester)
[![NPM version](https://badge.fury.io/js/hexo-fs.svg)](https://www.npmjs.com/package/hexo-fs)
[![Coverage Status](https://img.shields.io/coveralls/hexojs/hexo-fs.svg)](https://coveralls.io/r/hexojs/hexo-fs?branch=master)

File system module for [Hexo].

## Features

- Support for both Promise and callback interface.
- Use [graceful-fs] to avoid EMFILE error and various improvements.
- Use [chokidar] for consistent file watching.

## Installation

``` bash
$ npm install hexo-fs --save
```

## Usage

``` js
const fs = require('hexo-fs');
```

> Some methods in the original fs module are not listed below, but they're available in hexo-fs.

### exists(path)

Test whether or not the given `path` exists by checking with the file system.

### existsSync(path)

Synchronous version of `fs.exists`.

### mkdirs(path)

Creates a directory and its parent directories if they does not exist.

### mkdirsSync(path)

Synchronous version of `fs.mkdirs`.

### writeFile(path, data, [options])

Writes data to a file.

Option | Description | Default
--- | --- | ---
`encoding` | File encoding | utf8
`mode` | Mode | 438 (0666 in octal)
`flag` | Flag | w

### writeFileSync(path, data, [options])

Synchronous version of `fs.writeFile`.

### appendFile(path, data, [options])

Appends data to a file.

Option | Description | Default
--- | --- | ---
`encoding` | File encoding | utf8
`mode` | Mode | 438 (0666 in octal)
`flag` | Flag | w

### appendFileSync(path, data, [options])

Synchronous version of `fs.appendFile`.

### copyFile(src, dest, [callback])

Copies a file from `src` to `dest`.

### copyDir(src, dest, [options])

Copies a directory from `src` to `dest`. It returns an array of copied files.

Option | Description | Default
--- | --- | ---
`ignoreHidden` | Ignore hidden files | true
`ignorePattern` | Ignore files which pass the regular expression |

### listDir(path, [options])

Lists files in a directory.

Option | Description | Default
--- | --- | ---
`ignoreHidden` | Ignore hidden files | true
`ignorePattern` | Ignore files which pass the regular expression |

### listDirSync(path, [options])

Synchronous version of `fs.listDir`.

### readFile(path, [options])

Reads the entire contents of a file.

Option | Description | Default
--- | --- | ---
`encoding` | File encoding | utf8
`flag` | Flag | r
`escape` | Escape UTF BOM and line ending in the content | true

### readFileSync(path, [options])

Synchronous version of `fs.readFile`.

### emptyDir(path, [options])

Deletes all files in a directory. It returns an array of deleted files.

Option | Description | Default
--- | --- | ---
`ignoreHidden` | Ignore hidden files | true
`ignorePattern` | Ignore files which pass the regular expression |
`exclude` | Ignore files in the array |

### emptyDirSync(path, [options])

Synchronous version of `fs.emptyDir`.

### rmdir(path)

Removes a directory and all files in it.

### rmdirSync(path)

Synchronous version of `fs.rmdir`.

### watch(path, [options])

Watches changes of a file or a directory.

See [Chokidar API](https://github.com/paulmillr/chokidar#api) for more info.

### ensurePath(path)

Ensures the given path is available to use or appends a number to the path.

### ensurePathSync(path)

Synchronous version of `fs.ensurePath`.

### ensureWriteStream(path, [options])

Creates the parent directories if they does not exist and returns a writable stream.

### ensureWriteStreamSync(path, [options])

Synchronous version of `fs.ensureWriteStream`.

## License

MIT

[graceful-fs]: https://github.com/isaacs/node-graceful-fs
[Hexo]: https://hexo.io/
[chokidar]: https://github.com/paulmillr/chokidar