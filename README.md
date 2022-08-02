# pob-dict

Dictionary and config files for 
[Path Of Building Community](https://github.com/PathOfBuildingCommunity/PathOfBuilding) (POBC) 
code development in [VSCode](https://code.visualstudio.com/) 
with the [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) 
extension.

## Components
| Filename        | Description
| --------------- | -----------
| `settings.json` | VSCode workspace settings.
| `cspell.json`   | [CSpell](https://cspell.org/) settings.
| `poe-dict.txt` | Plaintext list of valid words specific to [Path of Exile](https://www.pathofexile.com/), with any "`'s`" removed.
| `pob-dict.txt` | Plaintext list of words deemed acceptable for use with developing the POBC source-code.

## Installation
* Ensure [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) 
VSCode extension is installed.
* Checkout or download & unzip this repo.
* Copy the component files listed above to the `.vscode` folder of your POBC repo.
* NOTE:  If `settings.json` already exists in your repo, you'll need to append this one 
to it.

## Example command-line usage
If you also have the [CSpell NPM package](https://www.npmjs.com/package/cspell) installed, 
you can initiate a full scan of your POBC repo from a VSCode terminal using a command like this:
```powershell
cspell --config C:\PathOfBuilding\.vscode\cspell.json --root C:\PathOfBuilding\ --relative --show-context --no-progress "**"
```

---

## Licence

[MIT](https://opensource.org/licenses/MIT)
