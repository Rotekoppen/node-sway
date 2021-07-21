# node-sway

Fork of [node-i3](https://github.com/sidorares/node-i3) to instead target sway.

## Install

	npm install git+https://github.com/Rotekoppen/node-sway

## API

### sway.command(<command>)

Sends the <command> to sway, very much alike running swaymsg <command>

### Get functions

All theese functions work the same way, they fetch something and passes it to an callback.

#### sway.workspaces(<callback>)

Gets the workspaces and passes it to the callback

#### sway.outputs(<callback>)

Gets the outputs and passes it to the callback

#### sway.tree(<callback>)

Gets the tree and passes it to the callback

#### sway.marks(<callback>)

Gets the marks and passes it to the callback

#### sway.barConfig(<callback>)

Gets the bar config and passes it to the callback

#### sway.version(<callback>)

Gets the version and passes it to the callback

#### sway.modes(<callback>)

Gets the available modes and passes it to the callback

#### sway.mode(<callback>)

Gets the active mode and passes it to the callback

#### sway.config(<callback>)

Gets the top level config file and passes it to the callback

#### sway.seats(<callback>)

Gets the seats and passes it to the callback

#### sway.inputs(<callback>)

Gets the inputs and passes it to the callback

## Examples

### Move the focus to the left, and subscribe to workspace events

```js
var sway = require('node-sway').createClient();
sway.command('focus left');
sway.on('workspace', function(w) {
  console.log('workspace event!', w);
})
```

### Get inputs

```js
var sway = require('node-sway').createClient();
sway.inputs(console.log);
})
```

### Get Current mode and available modes

```js
var sway = require('node-sway').createClient();
sway.mode(console.log);
sway.modes(console.log);
})
```
