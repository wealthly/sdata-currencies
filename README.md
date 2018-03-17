# <img src="https://avatars1.githubusercontent.com/u/37033013?s=200&v=4" width="64" style="vertical-align:text-bottom"> sdata:currencies
A dataset of global fiat currencies considered to be in circulation by their respective central banks and tradable on open markets. The verified JSON dataset can be downloaded [here](https://raw.githubusercontent.com/Wealthly/sdata-currencies/master/dist/data.json).

## Data Generation
This dataset is updated daily by an automated data service with changes pushed to the [automated](../automated) branch. The data service pulls data in from 4 distinct sources on the web and then aggregates, consolidates and sanitizes the data. The sources include several forex exchanges and wikis; each currency must exist on 3 or more of the 4 sources to be included in the dataset. After the initial dataset is generated, any overrides manually defined in [src/overrides.json5](src/overrides.json5) are merged with the dataset. The final dataset is then written, as a JSON array in alphabetical order by their ISO defined three letter currency code (code), to [dist/data.json](../automated/dist/data.json). If there are any new data changes, a commit is created and pushed by [devbot](https://github.com/wealthly-devbot) to the *automated* branch. Lastly, if there are no open pull-requests pending, devbot creates a new pull-request back to the *master* branch to be manually verified and merged, or rejected.

## Contributing and Issues
If you find incorrect data within the dataset, please create a pull-request with the corrections added to [src/overrides.json5](src/overrides.json5) or alternatively raise an [issue](../../issues/new).

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
