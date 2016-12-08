pome-data-plugin

Config data plugin for pome(a fast,scalable,distributed game server framework for Node.js. http://pome.netease.com), it can be used in pome(>=0.7.0).

pome-data-plugin is a config data(.csv) plugin for pome. pome-data-plugin can watch all config files in the given dir and reload the file automatically when it is modified.

##Installation

```
npm install pome-data-plugin
```

##Usage

```
var dataPlugin = require('pome-data-plugin');
... ...
app.configure('production|development', function() {
  ...
  app.use(dataPlugin, {
    watcher: {
      dir: __dirname + '/config/data',
      idx: 'id',
      interval: 3000
    }
  });
  ...
});
... ...
... ...
var npcTalkConf = app.get('dataService').get('npc_talk');
... ...
... ...
```

Please refer to [pome-data-plugin-demo](https://github.com/palmtoy/pome-data-plugin-demo)

