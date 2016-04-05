# bitmovin-player-akamai-analytics


### Player Reporting Events
Each EventHandler function takes exactly one argument: a callback function which is called when the event is fired. This callback function shall also have one argument. This is a _JSON_ object which provides additional information for the event.
For all events the object (which is passed to the callback function) has the following attributes:

```javascript
{
  timestamp: 1412171690785,
  type: 'onPlay'
}
```

**timestamp** -  A timestamp in milliseconds when the event occurred and type the name of the fired event.

**type** - The type of the event.

#### Add an Event Handler
To add an event handler, you can simply add the dedicated event to the _events_ section of the config object.

Example:

```javascript
events: {
  onReady : myFunc,
  onPlay  : function() {
              // do some awesome stuff
            },
  onError : myErrorHandlingFunc
}
```

We describe this approach in more detail in the [player configuration documentation](https://bitmovin.com/player-configuration/).

It is also possible to call ```addEventHandler``` with the event type and a callback function as parameter.

Example:

```javascript
addEventHandler('onReady', function(data) { ... });
```

#### Remove an Event Handler
To remove an event handler call ```removeEventHandler``` with the event type and callback function as parameter.

Example:

```javascript
removeEventHandler('onReady', function(data) { ... });
```

#### Further Reading and Available Events
More information about the <a href="https://bitmovin.com/player-api/" target="_blank">API</a> and all available <a href="https://bitmovin.com/player-api/#Available_Events" target="_blank">Events</a> can be found in our <a href="https://bitmovin.com/support/" target="_blank">support section</a>.

