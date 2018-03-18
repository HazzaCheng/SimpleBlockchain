# SimpleBlockchain
A simple implementation for blockchain.

## Usage

You need to run the server firstly, you can set the port and it use the localhost as default.
```
python blockchain.py -p <your port>
```

You can use crul or Postman to make GET or POST requests, and all the APIs are following:

- Mine the block
```
curl -X GET "http://<url:port>/mine"
```

- Add the transactions
```
curl -X POST -H "Content-Type: application/json" -d '{
                             "sender": <your sender>,
                             "recipient": <your recipient>, 
                             "amount": <your amount>
                            }' "http://<url:port>/transactions/new"
```

- Get all the blocks
```buildoutcfg
curl -X GET "http://<url:port>/chain"
```

- Register the nodes
```
curl -X POST -H "Content-Type: application/json" -d '{
                             "nodes": [<url:port>, <url:port>]
                            }' "http://<url:port>/nodes/register"
```

- Resolve the conflicts
```
curl -X GET "http://<url:port>/nodes/resolve"
```
