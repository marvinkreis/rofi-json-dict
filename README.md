
## Description

Reads all JSON files in a directory (default: `XDG_DATA_HOME/rofi-json-dicts`) as dictionaries and lets the user query translations.

![Screenshot](https://marvinkreis.github.io/rofi-plugins/rofi-dict/example.png)

### Dictionaries

Dictionaries have the following structure:

```json
{
    "key1": "value1",
    "key2": "value2",
    "key3": "value3"
}
```
They must be saved in UTF-8 with the `.json` file extension.

The `convert-dict` python script can be used to convert [FreeDict dictionaries](https://github.com/freedict/fd-dictionaries) into the JSON format.

### Matching modes

This plugin supports three matching modes:

#   | Mode                 | Description
--- | -------------------- | -----------
0   | exact                | match if the key matches the search string exactly
1   | substring            | match if the key contains the search string
2   | Levenshtein distance | match if the [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) is below a threshold (default: 2)

### Key-Bindings

Key                                                  | Action
---------------------------------------------------- | ------
`kb-mode-next` <br/> (default: `Shift+Right`)        | Switch to the next matching mode. <br/> Switch to the next rofi-mode if the last matching mode is already selected.
`kb-mode-previous` <br/> (default: `Shift+Left`)     | Switch to the previous matching mode. <br/> Switch to the previous rofi-mode if the first matching mode is already selected.
`kb-accept-custom` <br/> (default: `Control+Return`) | Switch to the next matching mode (only if the input is empty).

### Command line options / Configuration

Option            | Arguments            | Description
----------------- | -------------------- | -----------
`-json-dict-path` | `/path/to/directory` | Sets the dictionary directory (default: `XDG_DATA_HOME/rofi-json-dicts`).
`-json-dict-mode` |  `[0 | 1 | 2]`       | Sets the matching mode (default: 0).

The source file contains more configuration via `#define`.



## Compilation

### Dependencies

| Dependency | Version |
| ---------- | ------- |
| rofi       | 1.4     |
| json-c     | 0.13    |

### Installation

Use the following steps to compile the plugin with the **autotools** build system:

```bash
autoreconf -i
./configure
make
make install
```
