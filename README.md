# detect-character-encoding

> Detect character encoding using [ICU](http://site.icu-project.org)

**Tip:** If you don’t need ICU in particular, consider using [ced](https://github.com/sonicdoe/ced), which is based on Google’s lighter [compact_enc_det](https://github.com/google/compact_enc_det) library.

## Installation

```console
$ npm install detect-character-encoding
```

detect-character-encoding is a C++ addon. Therefore, you may need to install various build tools. Check [node-gyp’s readme](https://github.com/nodejs/node-gyp#installation) for more information.

## Usage

```js
const fs = require('fs');
const detectCharacterEncoding = require('detect-character-encoding');

const fileBuffer = fs.readFileSync('file.txt');
const charsetMatch = detectCharacterEncoding(fileBuffer);

console.log(charsetMatch);
// {
//   encoding: 'UTF-8',
//   confidence: 60
// }
```

detect-character-encoding may return `null` if no charset matches.

## Supported operating systems

- macOS Big Sur
- Ubuntu 20.04 and 18.04
- Debian 11, 10, and 9

detect-character-encoding does not support 32-bit operating systems.

## Supported character sets

As listed in [ICU’s user guide](http://userguide.icu-project.org/conversion/detection#TOC-Detected-Encodings):

- UTF-8
- UTF-16BE
- UTF-16LE
- UTF-32BE
- UTF-32LE
- Shift_JIS
- ISO-2022-JP
- ISO-2022-CN
- ISO-2022-KR
- GB18030
- Big5
- EUC-JP
- EUC-KR
- ISO-8859-1
- ISO-8859-2
- ISO-8859-5
- ISO-8859-6
- ISO-8859-7
- ISO-8859-8
- ISO-8859-9
- windows-1250
- windows-1251
- windows-1252
- windows-1253
- windows-1254
- windows-1255
- windows-1256
- KOI8-R
- IBM420
- IBM424

## License

detect-character-encoding is licensed under the BSD 2-clause license but includes third-party software under different licenses. See [`LICENSE.md`](./LICENSE.md) for the full license text.
