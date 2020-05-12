# vuex-store-module
`VuexStoreModule` is a generic vuex store for keep it simple. Use your time for what you really needs.

## Getting Started

### Installation

```js
npm i store-module-test
```

### Usage

To use the `VuexStoreModule` you have to setup the API, you can pass an instance of axios or another API like axios.

```js
import VuexStoreModule from 'vuex-store-module'
import axios from 'axios'

const storeModule = new VuexStoreModule({ apiService: axios })
// you can pass your own api like axios to apiService

export default storeModule
```

Inside your `store` let's import our instance of `VuexStoreModule`.

```js
import storeModule from 'some-path'

export default storeModule.createStoreModule('posts')
```

### Options

```js
const storeModule = new VuexStoreModule({
	apiService: undefined // intance of API
})

storeModule.createModule(
  resource, // name of store and usually used as endpoint of API
  options: {
    idAttribute: 'id', // property used for find in object and arrays
    perPage: 12, // results per page
    fetchFiltersURL: undefined, // custom URL for fechFiltersURL
    replaceURL: undefined, // custom URL for replaceURL
    fetchSingleURL: undefined, // custom URL for fetchSingleURL
    methods: [ // methods that the VuexStoreModule will return
      'CREATE',
      'DESTROY',
      'FETCH_FILTERS',
      'FETCH_FORM',
      'FETCH_LIST',
      'FETCH_SINGLE',
      'REPLACE',
      'UPDATE'
    ]
  }
)
```
