# \<y-element\>

> Polymer Web Component for sharing data with [Yjs](https://github.com/y-js/yjs/). Perform data-binding on shared data!

[Read the docs](http://y-js.org/y-element/) to get started!

This repository contains four elements:

* [y-element](//y-js.org/y-element/components/y-element/#y-element) - Configures the database and connector information
* [y-map](//y-js.org/y-element/components/y-element/#y-map) - Creates a map type. It exports the data as a shared javascript object
* [y-array](//y-js.org/y-element/components/y-element/#y-array) - Creates an array type. It exports the data as a shared javascript array
* [y-type](//y-js.org/y-element/components/y-element/#y-type) - Configuration for any Yjs type. It exports the Yjs type

##### Simple Yjs example in Javascript
```
Y({
  db: {
    name: 'memory'
  },
  connector: {
    name: 'websockets-client',
    room: 'example'
  },
  share: {
    map: 'Map'
  }
}).then(function (y) {
  y.share.map // is the shared map type
})
```

##### Same example in Polymer
```
<y-element
  db-name="memory"
  connector-name="websockets-client"
  connector-room="example">
  <y-map name="map" data="{{myMap}}"></y-map>
</y-element>
```

### Before you start
Before you start remember to install all y-* you want to use. In particular you need to install a connector (e.g. `y-websockets-client`), and a database adapter (e.g. `y-memory`). `yjs`, `y-map`, and `y-array` are dependencies of `y-element`.

```
bower i --save y-element y-memory y-websockets-client
``` 

## Contribute
Issues and Pull requests are very much welcome. If you want to help out you can also contribute to the docs ;) This project was build with [Polymer CLI](https://www.npmjs.com/package/polymer-cli) v0.16. Make sure the tests are still running ;)

## License
y-element is licensed under the [MIT License](./LICENSE).

<yjs@dbis.rwth-aachen.de>