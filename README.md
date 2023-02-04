# pob-dict

Dictionaries and [Code Spell Checker](https://cspell.org/) (CSpell) config files for [Path Of Building Community](https://github.com/PathOfBuildingCommunity/PathOfBuilding) (PoB) code development. 

## Components
| Filename                       | Description
| ------------------------------ | -----------
| [`cspell.json`](cspell.json)   | CSpell settings.
| [`poe-dict.txt`](poe-dict.txt) | Plaintext list of valid words specific to [Path of Exile](https://www.pathofexile.com/).
| [`pob-dict.txt`](pob-dict.txt) | Plaintext list of valid words for developing the PoB source-code.
| [`ignore-dict.txt`](ignore-dict.txt) | Plaintext list of known misspellings that are not to be reported, because Reasons™.
| [`spellcheck.yml`](docs/spellcheck.yml) | Example GitHub workflow using [`cspell-action`](https://github.com/streetsidesoftware/cspell-action).

## Installation

### PoB repo
* Copy `docs/spellcheck.yml` to `.github/workflows/` of the PoB repo.

This workflow is designed to be run from the PoB repo, collecting files from this repo as needed, and thus
avoids cluttering the PoB repo.  By default the workflow automatically only checks changes made in pull-requests against the `dev` branch.  
It can also be triggered manually to perform a full check of a specific branch/tag/SHA.


### VSCode <sup><sub>(optional)</sub></sup>
* Install [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker).
* Checkout (or download & unzip) this repo to a directory that shares its parent dir with your PoB fork.
* Add the following lines to `.vscode/settings.json` in your PoB fork:
```json
{
  "cSpell.import": [ "../../pob-dict/cspell.json" ],
  "cSpell.language": "en,en-GB"
}
```


### Command-line <sup><sub>(optional)</sub></sup>
* Install the [CSpell NPM package](https://www.npmjs.com/package/cspell).

To run a full scan of a local PoB fork with some helpful options enabled:
```powershell
PS C:\PathOfBuilding> cspell --config "..\pob-dict\cspell.json" --relative --show-context --no-progress "**"
```

## Dictionary additions
To which dictionary do I add this unknown word?
* If it's spelled *correctly within the context of*:
  * the game (Path of Exile) -> `poe-dict.txt`.
  * the PoB source code / git repository -> `pob-dict.txt`.
* If it's spelled *incorrectly* but you want to suppress the warning -> `ignore-dict.txt`.  To reduce false negatives, please try to make this type of addition as specific as possible.

**Note:**  Please do not add apostrophes / possessives (`'s`) to any words in any dictionary.

### Examples
| Word            | Dictionary          | Reason
|-----------------|---------------------|------------------------------
| Atziri          | `poe-dict.txt`      | Correct spelling of PoE NPC.
| REGENPERCENT    | `pob-dict.txt`      | Correct combination of two words, used in PoB source code.
| Lilylicious     | `pob-dict.txt`      | Correct spelling of a PoB contributor's name/handle.
| CritsDontAlways | `ignore-dict.txt`   | Incorrect spelling/punctuation but we want to suppress the warning.


---

## License

[MIT](https://opensource.org/licenses/MIT)
