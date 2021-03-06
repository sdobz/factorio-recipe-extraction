# Factorio Recipe Extraction

[![npm](https://img.shields.io/npm/v/factorio-recipe-extraction.svg)](https://www.npmjs.com/package/factorio-recipe-extraction)
[![Build Status](https://travis-ci.org/CodeLenny/factorio-recipe-extraction.svg?branch=master)](https://travis-ci.org/CodeLenny/factorio-recipe-extraction)
[![Coverage Status](https://coveralls.io/repos/github/CodeLenny/factorio-recipe-extraction/badge.svg?branch=master)](https://coveralls.io/github/CodeLenny/factorio-recipe-extraction?branch=master)

Extracts recipes and items from [Factorio][], including recipes added from mods.

<div style="text-align: center;">
  <img src="http://i.imgur.com/2xhn74P.png" />
</div>

## Command Line Usage

Install NodeJS (v6 or later), and make sure Lua is installed on your system.
You may need to also install `g++`.

Install system-wide:
```bash
npm install --global factorio-recipe-extraction
factorio-extractor --output recipes.json --data ~/.factorio
```

Install into the local directory:
```bash
npm install factorio-recipe-extraction
$(npm bin)/factorio-extractor # ...
```

## Programmatic Usage

A NodeJS API allows you to use the recipe extractor in your own projects.

```bash
npm install --save factorio-recipe-extraction
```

```js
const path = require("path");
const Extractor = require("factorio-recipe-extraction");

let extractor = new Extractor("~/.factorio", path.join(__dirname, "data-output.json"));
extractor
  .extract()
  .then(() => {
    console.log("Finished extracting Factorio data.");
  });
```

[Full `Extractor` documentation][api-Extractor]

## Acknowledgements

Thanks go out to Nicholas Powell for creating [Foreman][foreman], from which the basic structure for recipe extraction
was based upon.

[Factorio]: https://www.factorio.com/
[api-Extractor]: https://codelenny.github.io/factorio-recipe-extraction/Extractor.html
[foreman]: https://bitbucket.org/Nicksaurus/foreman/
