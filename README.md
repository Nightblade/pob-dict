# pob-words

## Description
Dictionary and config files for [Path Of Building Community](https://github.com/PathOfBuildingCommunity/PathOfBuilding) (POBC) code development in [VSCode](https://code.visualstudio.com/) with the [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) extension.

## Components
| Filename        | Description
| --------------- | -----------
| `settings.json` | VSCode workspace settings.
| `cspell.json`   | [CSpell](https://cspell.org/) settings.
| `poe-words.txt` | List of valid [Path of Exile](https://www.pathofexile.com/) words.  <br />Straight plaintext with "`'s`" stripped.
| `pob-words.txt` | List of words specific to the POBC source-code.  <br />This helps to reduce spell-checking noise.  <br />Plaintext as above but with word-joining hints ("+") for CSpell


## Installation
* Ensure [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) VSCode extension is installed.
* Download `pob-words` and unpack.
* If you already have a `settings.json` file in your `.vscode` folder, append mine to yours.
* Move/copy the remaining component files listed above to the `.vscode` folder of your POBC repo.

## Example command-line usage
If you also have the [CSpell NPM package](https://www.npmjs.com/package/cspell) installed, you can initiate a full scan of your POBC repo from a VSCode terminal and it will use the settings in your `.vscode` folder:
```powershell
cspell "**"
```

---

## Licence

[MIT](https://opensource.org/licenses/MIT)
