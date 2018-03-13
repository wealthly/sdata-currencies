# <div style="display:inline-block;width:64px;height:64px;overflow:hidden;margin:0;padding:0;"><img src="https://avatars1.githubusercontent.com/u/37033013?s=200&v=4" width="64" height="64" style="vertical-align:text-bottom;margin-bottom:-40px;"></div> sdata:currencies
A dataset of global fiat currencies considered to be in circulation by their respective central banks and tradable on open markets. The verified JSON dataset can be downloaded [here](https://raw.githubusercontent.com/Wealthly/sdata-currencies/master/dist/data.json).

## Data Generation
This dataset is updated daily by an automated service which pulls data in from 4 distinct sources on the web, then consolidates and sanitizes the data. The sources include several exchanges and wikis, while each currency must exist on 3 or more of the 4 sources to be included in the dataset. After the initial dataset is generated, any overrides manually defined in [src/overrides.json5](src/overrides.json5) are merged with the dataset. The final dataset is then written to [dist/data.json](../automated/dist/data.json) in the *automated* branch as a JSON array in alphabetical order by currency code. Every day there is a commit pushed by our [devbot](https://github.com/wealthly-devbot) to the *automated* branch, regardles if there were any changes, this is to flag that the automated service successfully completed. If changes were committed, then devbot will raise a pull-request back to the *master* branch.

## Contributing and Issues
If you find incorrect data within the dataset, please create a pull-request with the corrections added to the [src/overrides.json5](src/overrides.json5) data file or alternatively raise an [issue](../../issues/new).

## Example JSON
```javascript
[
  {
    "code": "CAD",
    "numeric": "124",
    "decimals": 2,
    "symbol": "$",
    "name": "Canadian Dollar",
    "shortName": "Dollar"
  }
]
```
