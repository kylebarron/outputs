# transforms

This monorepo contains a collection of nteract transforms. Transforms are React components that take Jupyter display objects as inputs and render rich views as outputs.

## Installation

To use the basic set of transforms, you can use the `@nteract/outputs` package.

```
$ npm install --save @nteract/outputs
```

## Usage

The example below shows how we can use the `ExecuteResult` component within the `@nteract/outputs` package to render the response to an execution request sent by our Jupyter kernel.

```javascript
import { ExecuteResult } from "@nteract/outputs";

export default () => {
  const Plain = props => <pre>{props.data}</pre>;
  Plain.defaultProps = {
    mediaType: "text/plain"
  };

  return (
    <ExecuteResult data={{ "text/plain": "The answer to everything is 42." }}>
      <Plain />
    </ExecuteResult>
  );
};
```

Usage instructions for other transforms are documented within each transform's README.

## Documentation

Transforms are documented in the [docs](./docs) directory.

## Support

If you experience an issue while using this package or have a feature request, please file an issue on the [issue board](https://github.com/nteract/outputs/issues).

## License

[BSD-3-Clause](https://choosealicense.com/licenses/bsd-3-clause/)
