# Blockbook Docker

Docker container for Blockbook, the Trezor wallet backend. 

To run, just pass the RPC details (user, pass, rpc host, rpc port and zmq socket port) from your Bitcoin full node as env variables:

```
docker run --name blockbook -it -p 7030:7030 -p 7130:7130 -e RPC_USER=myuser -e RPC_PASS=pass \
Obyno1010/blockbook
```

It will start syncing and the progress can be checked at https://localhost:7130

In your Trezor wallet, go to "Wallet Settings" and in the "Bitcore Server URL" put the URL above.


## Stopping gracefully

To stop the container gracefully (and have the database files preserved), do a ```docker stop -t 60 blockbook``` and to restart it later, ```docker start blockbook```.

