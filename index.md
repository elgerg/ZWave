# ZWave
ZWave Documentation...

This readme is to help people who have a working ZWave network access specific weird undocumented command classes etc.

I Set this up as i use an Assa abloy (Yale) ZWave module (SD-M1100) for the Conexis L1 smart lock with Node-red.

https://yalehome.co.uk/z-wave-module-2/

https://yalehome.co.uk/conexis-l1-chrome/

So far the following commands work and give responses as expected (assuming the node is node 5):

## Unlock remotely:
### Request:
```javascript
msg.topic = 'setValue'

msg.payload = {
    "nodeid":5,
    "cmdclass":98,
    "instance":1,
    "cmdidx":0,
    "value":false
    
}
```

### Response:
```json
{
    "value_id": "5-98-1-0",
    "node_id": 5,
    "class_id": 98,
    "type": "bool",
    "genre": "user",
    "instance": 1,
    "index": 0,
    "label": "Locked",
    "units": "",
    "help": "",
    "read_only": false,
    "write_only": false,
    "min": 0,
    "max": 0,
    "is_polled": false,
    "value": false
}{
    "value_id": "5-98-1-1",
    "node_id": 5,
    "class_id": 98,
    "type": "list",
    "genre": "user",
    "instance": 1,
    "index": 1,
    "label": "Locked (Advanced)",
    "units": "",
    "help": "",
    "read_only": false,
    "write_only": false,
    "min": 0,
    "max": 0,
    "is_polled": false,
    "values": ["Unsecure", "Unsecured with Timeout", "Inside Handle Unsecured", "Inside Handle Unsecured with Timeout", "Outside Handle Unsecured", "Outside Handle Unsecured with Timeout", "Secured", "Invalid"],
    "value": "Unsecure"
}{
    "value_id": "5-113-1-0",
    "node_id": 5,
    "class_id": 113,
    "type": "byte",
    "genre": "user",
    "instance": 1,
    "index": 0,
    "label": "Alarm Type",
    "units": "",
    "help": "",
    "read_only": true,
    "write_only": false,
    "min": 0,
    "max": 255,
    "is_polled": false,
    "value": 25
}{
    "value_id": "5-113-1-1",
    "node_id": 5,
    "class_id": 113,
    "type": "byte",
    "genre": "user",
    "instance": 1,
    "index": 1,
    "label": "Alarm Level",
    "units": "",
    "help": "",
    "read_only": true,
    "write_only": false,
    "min": 0,
    "max": 255,
    "is_polled": false,
    "value": 1
}

```
## Request battery level:

### Request:
```javascript
msg.topic = 'refreshValue'

msg.payload = {
    'args': [5, 128, 1, 0]
};
```

### Response:
```json
{
    "value_id": "5-128-1-0",
    "node_id": 5,
    "class_id": 128,
    "type": "byte",
    "genre": "user",
    "instance": 1,
    "index": 0,
    "label": "Battery Level",
    "units": "%",
    "help": "",
    "read_only": true,
    "write_only": false,
    "min": 0,
    "max": 255,
    "is_polled": false,
    "value": 43
}
```

# Contribution
Talk to me, tell me what I can add. Put in a PR. I'm open to gaining as much info in this as I can and sharing it.

Thanks!
