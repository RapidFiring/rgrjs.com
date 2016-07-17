RGR.js
# Features and Dependencies used

prototype developed with Pluralsight Course [Building Data-driven React Applications with Relay, GraphQL, and Flux](https://app.pluralsight.com/library/courses/react-apps-with-relay-graphql-flux/table-of-contents)

## used dependencies ##
````
npm install -g webpack@beta
npm install --save babel@6 babel-core@6 babel-loader@6
npm install --save react react-dom
npm install --save babel-preset-react babel-preset-es2015
npm install --save babel-cli@6
````
### webpack.config.js ###
````
define root/webpack.config.js
  module.exports = {
    entry: "./prototype/js/app.js",
    output: {
      path: __dirname + "/prototype",
      filename: "bundle.js"
    }
    // loaders...
    module: {
      loaders[
        //{test: ..,loader: ...}

      ]
    }
  }
````
### webpack commandline ###
````
webpack <options>
  <option>
  -w  autorebuild if something changes
  -d error trace in maped file
  --displayerror-details
````

## flux-pattern ##

  ->  ACTION <-> API/DATA
  |      |
  |   Dispatcher
  |      |
  |   Store
  |      |
  --  View

  ### Actions ###
  - Objects/Data
  - "type" property: How to use the action
  - Action Creators: Methods in a module
  - "API" od the application (harhar)

    e.x.
  ````
  import AppDispatcher from '...'
  import ActionTypes from '...'

  export default {
    receiveData(data) {
      AppDispatcher.dispatch({
        actionType: ActionTypes.RECEIVE_DATA, data
      })
    },
  }
  ````

  ### Dispatcher ###
  - registry of fallbacks
  - fixed, singleton `A.waitFor(B)`
  - Payload is an action)
  - Flux.Dispatcher() `github.com/facebook/flux`
  - dispatch(), register(), waitFor()

  ````

  // AppDispatcher.js
  import *Flux* from 'flux';

  // Export a singleton
  export default *new Flux.Dispatcher()*;
  ````
