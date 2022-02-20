# pob-words

## Description
Dictionary and config files for [Path Of Building Community](https://github.com/PathOfBuildingCommunity/PathOfBuilding) code development in [VSCode](https://code.visualstudio.com/) with the [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) extension.

## Contents
* `settings.json` VSCode workspace settings.
* `cspell.json` [cSpell](https://cspell.org/) settings.
* `poe-words.txt` Plaintext list of [Path of Exile](https://www.pathofexile.com/) words.
* `pob-words.txt` List of POBC source-code words.  Might contain some cSpell-specific patterns where needed.

## How to install
This my current setup, which is installed outside my POBC development repo to avoid introducing unnecessary files.
* Download pob-words and unpack it into a folder one level higher than your POBC repo.
* Move/copy my `settings.json` to the `.vscode` folder of your POBC repo.  (If your file already exists, append the contents of my file to yours.)

## Command-line usage example
To initiate a full scan of your POBC repo from a VSCode terminal:
```bash
cspell --config "..\pob-words\cspell.json" *
```


## Licence

[MIT](https://opensource.org/licenses/MIT)