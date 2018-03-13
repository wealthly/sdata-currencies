# sdata-currencies
A static dataset of global fiat currencies which are considered to be in circulation by their respective central banks and tradable on market exchanges.

This dataset is updated daily by an automated service which pulls data in from 4 distinct sources on the web and then sanitizes the data.  The sources include several exchanges and wikis, each currency must exist on 3 or more of the 4 sources to be included in the dataset.  After the initial dataset is generated, any overrides provided by the src/overrides.json5 data file are merged into the dataset.  The final dataset is then written to dist/data.json as a JSON array in alphabetical order by currency code.

If you see any incorrect data within the dataset, please create a pull-request with your corrections in the src/overrides.json5 data file or alternatively raise an issue.
