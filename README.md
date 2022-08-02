# pob-dict

Dictionary and config files for 
[Path Of Building Community](https://github.com/PathOfBuildingCommunity/PathOfBuilding) (POBC) 
code development in [VSCode](https://code.visualstudio.com/) 
with the [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) 
extension.

## Components
| Filename       | Description
| -------------- | -----------
| `cspell.json`  | [CSpell](https://cspell.org/) settings.
| `poe-dict.txt` | Plaintext list of valid words specific to [Path of Exile](https://www.pathofexile.com/), with any "`'s`" removed.
| `pob-dict.txt` | Plaintext list of words deemed acceptable for use with developing the POBC source-code, with any "`'s`" removed.

## Installation
* Ensure [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) 
VSCode extension is installed.
* Checkout (or download & unzip) this repo to a sub-directory that shares its parent dir with your POBC repo.
* Add the following lines to `settings.json` in the `.vscode` folder of your POBC repo:
```json
{
  "cSpell.import": [ "../../pob-dict/cspell.json" ],
  "cSpell.language": "en,en-GB"
}
```

## Command-line usage
If you also have the [CSpell NPM package](https://www.npmjs.com/package/cspell) installed 
you can initiate a full scan of your POBC repo from a VSCode terminal using a command like this:
```powershell
cspell --config "..\pob-dict\cspell.json" --relative --show-context --no-progress "**"
```

---

## Licence

[MIT](https://opensource.org/licenses/MIT)
