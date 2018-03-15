# Web examples

You can use [serve](https://www.npmjs.com/package/serve) to run a simple static file server for the examples included.

Run `serve` via [npx](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b) that comes bundles with npm.

`$ npx serve web`

## Examples

Examples as seen [here](https://bl.ocks.org/vasturiano/f59675656258d3f490e9faa40828c0e7)

- Les Miserables character connections (Book/Play)
- Blocks
- D3 dependencies

#### 3D example

Go to [http://localhost:5000/3d](http://localhost:5000/3d) in your browser

#### 3D VR example

Go to [http://localhost:5000/vr](http://localhost:5000/vr) in your browser

### Custom examples

Please add your own examples/configuration in similar fashion :)

## Data

The datasets used:

- [3d-force-graph: example/datasets](https://github.com/vasturiano/3d-force-graph/tree/master/example/datasets)
- [d3.csv](https://bl.ocks.org/mbostock/9a8124ccde3a4e9625bc413b48f14b30#d3.csv)

These datasets are used for both the 3D and 3D VR examples, and have been included in the `web/data` folder. The datasets are loaded in the `data-set-loader.js`

```js
function getGraphDataSets() {

  const loadMiserables = function (Graph) {
    Graph
      .nodeLabel('id')
      .nodeAutoColorBy('group')
      .jsonUrl('/data/miserables.json');
  };
  loadMiserables.description = "<em>Les Miserables</em> data (<a href='https://bl.ocks.org/mbostock/4062045'>4062045</a>)";

  // ...
}
```

Here is a [code snippet for updating the graph state](https://github.com/vasturiano/three-forcegraph/blob/master/src/forcegraph-kapsule.js#L244) loading new data into the graph via `jsonUrl`.

We would like to do something similar, using a different strategy tham fetch, such as feeding new data from [automerge-graph](https://github.com/kristianmandrup/automerge-graph) instead.

Ideally it should just register a listener to whatever external datasource provider.
