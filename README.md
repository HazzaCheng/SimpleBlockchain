# SimpleBlockchain
A simple implementation for blockchain.

## Usage

You need to run the server firstly, you can set the port and it use the localhost as default.
``` commandline
python blockchain.py -p <your port>
```

We use flask to implement some APIs, you ou can use crul or Postman to make GET or POST requests, and all the fAPIs are following:

- Mine the block
``` commandline
curl -X GET "http://<url:port>/mine"
```

- Add the transactions
``` commandline
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
``` commandline
curl -X POST -H "Content-Type: application/json" -d '{
                             "nodes": [<url:port>, <url:port>]
                            }' "http://<url:port>/nodes/register"
```

- Resolve the conflicts
``` commandline
curl -X GET "http://<url:port>/nodes/resolve"
```

## Pipenv

If you use pipenv, you should do the following.

``` commandline
pip install pipenv 

pipenv --python=python3.6

pipenv install 

```

Run some servers as nodes:

- `pipenv run python blockchain.py -p 5555`
- `pipenv run python blockchain.py -p 5556`
- `pipenv run python blockchain.py --port 5557`

## Docker
You also can use Docker, you should do the following:
``` commandline
docker build -t blockchain
docker run --rm -p 80:5000 blockchain
```

Run some nodes:

- `docker run --rm -p 81:5000 blockchain`
- `docker run --rm -p 82:5000 blockchain`
- `docker run --rm -p 83:5000 blockchain`