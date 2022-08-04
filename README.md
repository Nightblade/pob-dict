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
| `poe-dict.txt` | Plaintext list of valid words specific to [Path of Exile](https://www.pathofexile.com/).
| `pob-dict.txt` | Plaintext list of valid words for developing the POBC source-code.
| `ignore-dict.txt` | Plaintext list of known misspellings that are not to be reported, because Reasons™.

## Dictionary additions
Which dictionary do I add this flagged word to?
* If it's spelled correctly and used in:
  * the Path of Exile game: `poe-dict.txt`.
  * the POB source code / git repository: `pob-dict.txt`.
* If it's spelled *incorrectly* but you don't want to be warned about it: `ignore-dict.txt`  Please try to make these as specific as possible to eliminate unwanted false negatives in future.

Examples:
| Word            | Dictionary          | Reason
|-----------------|---------------------|------------------------------
| Atziri          | `poe-dict.txt`      | Correct spelling of POE NPC.
| REGENPERCENT    | `pob-dict.txt`      | Correct combination of two words, used in POB source code.
| Lilylicious     | `pob-dict.txt`      | Correct spelling of a POB contributor's name/handle.
| CritsDontAlways | `ignore-dict.txt`   | Incorrect spelling but we are aware and don't want a warning. *(1)*

*(1)* Note that just adding the word "dont" to the ignore dict would most likely create unwanted false negatives elsewhere.

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
