# ZWave
ZWave Documentation...

This readme is to help people who have a working ZWave network access specific weird undocumented command classes etc.

I Set this up as i use an Assa abloy (Yale) ZWave module for the Conexis L1 smart lock with Node-red

So far the following commands work and give responses as expected (assuming the node is node 5):

##Request battery level:

###Request:
msg.topic = 'refreshValue'
msg.payload = {
    'args': [5, 128, 1, 0]
};

###Response:
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
