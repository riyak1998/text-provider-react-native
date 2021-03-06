<div align="center">
    <img
        width="200" height="200"
        src="./logo.png"
    />
    <h1>text-provider-react-native</h1>
    <p>
        A react-native component which provides all the string constants using provider pattern
    </p>
</div>

<div align="center">
    <a href="https://circleci.com/gh/intuit/text-provider-react-native">
        <img
            src="https://img.shields.io/circleci/project/github/intuit/text-provider-react-native/master.svg?style=flat-square&logo=circleci"
            alt="CircleCI"
        />
    </a>
    <a href="https://www.npmjs.com/package/text-provider-react-native">
        <img
            src="https://img.shields.io/npm/v/text-provider-react-native.svg?style=flat-square&logo=npm"
            alt="npm"
        />
    </a>
    <a href="https://github.com/intuit/text-provider-react-native/graphs/contributors">
        <img
            src="https://img.shields.io/badge/all_contributors-2-orange.svg?style=flat-square&logo=github"
            alt="All Contributors"
        />
    </a>
    <a href="https://www.npmjs.com/package/text-provider-react-native">
        <img
            src="https://img.shields.io/npm/dt/text-provider-react-native.svg?style=flat-square&logo=npm"
            alt="npm"
        />
    </a>
</div>


It provides two components:

1. [TextProvider](src/TextProvider/index.js)
2. [FormattedMessage](src/FormattedMessage/index.js)

## Install

```bash
npm i text-provider-react-native
```

## Usage

1. Import the string constants required for the particular presentational component:

```javascript
const sampleText = require("src/nls/sample-text.json");
```

2. Use the [TextProvider](src/TextProvider/index.js) to make it available for all the components:

```jsx
<TextProvider globalText={sampleText} >
  <MyPresentationalComponent />
</TextProvider>
```

3. Use it inside the presentational component:

```jsx
<FormattedMessage id="Random Id"/>
```

```jsx
const randomId = "Random Id";
const values = {
  "valueToBeInjected": "Random Value"
};

<FormattedMessage id={randomId} values={values}/>
```

Works like a format string also. Example JSON:

```json
{
  "Random Id": "<b>Random Text Returns</b> {valueToBeInjected} for each text)"
}
```

Then ``${valueToBeInjected}`` gets replaced with the value specified in `values`.

Make sure that a string by the same `id` exists in the JSON file.
