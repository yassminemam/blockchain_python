# blockchain_python
The github repository contains a basic implementation of a blockchain.

# Code implementation contains

# Part 1 - Building a Blockchain
By creating Blockchain class that has the main params/data_variables and the main functionality related to the blockchain it's self.

## Main params/data_variables of Blockchain class
1. chain list:: which is the list will be updated every time you mine a new block.
2. block:: is the current block which we are trying to mine using the blockchain class functions. Every block has it's own set of key value pair which are 'index', 'timestamp', 'proof', 'previous_hash'.  
3. new_proof:: is the value we are trying to find to be able to mine a new block.

## Main functionality of Blockchain class
1. fun `__init__` is the constructor of the Blockchain class, it initialize the chain list and create the very first block with proof of 1 and previous_hash equals to 0.
2. fun `create_block` it creates a new block as a new instance of the Blockchain class.
3. fun `get_previous_block` is for getting the previous block from the chain list and using it's previous_hash for th mining process.
4. fun `proof_of_work` to proof that the current proof is thr right value using hashlib and sha256 operation for hashing and make sure that the end value starts with '0000'.
5. fun `hash` using hashlib and sha256 operation for hashing values.
6. fun `is_chain_valid` to be able to check if the chain values and no fake values.

# Part 2 - Mining our Blockchain

## Creating a Web App
using Flask.

## Creating a Blockchain
creating a new instance from the Blockchain class.

## Mining a new block
using that new blockchain use this web based function mine_block to mine a new block.

## Getting the full Blockchain
using that new blockchain use this web based function get_chain to get the full chain.

## Checking if the Blockchain is valid
using that new blockchain use this web based function is_valid to check is_chain_valid.

## Running the app
```bash
$ FLASK_APP=blockchain.py flask run
* Running on http://localhost:5000/
```
Or run our app using the ide to be deployed and start testing it.

# Testing
## [Postman](https://www.getpostman.com/)
1. `GET http://127.0.0.1:5000/get_chain` which will initiate the chain and create the first block.
2. `GET http://127.0.0.1:5000/mine_block` which will mine a new block.
3. `GET http://127.0.0.1:5000/get_chain` which will get the new chain after mining that new block form the previous step.
4. Repeat mining step 2 for 5 times for example.
5. `GET http://127.0.0.1:5000/get_chain` again.
6. `GET http://127.0.0.1:5000/is_valid` to check if your chain is valid.

## [Httpie](https://httpie.org/)
```bash
# Install httpie
$ pip install httpie

$ http http://127.0.0.1:5000/get_chain
$ http http://127.0.0.1:5000/mine_block
$ http http://127.0.0.1:5000/get_chain
# Repeat http http://127.0.0.1:5000/mine_block 5 times.
$ http http://127.0.0.1:5000/get_chain
$ http http://127.0.0.1:5000/is_valid
```

## [Curl](https://curl.haxx.se/)
```bash
$ curl http://127.0.0.1:5000/get_chain
$ curl http://127.0.0.1:5000/mine_block
$ curl http://127.0.0.1:5000/get_chain
# Repeat curl http://127.0.0.1:5000/mine_block 5 times.
$ curl http://127.0.0.1:5000/get_chain
$ curl http://127.0.0.1:5000/is_valid
```

# Dependencies
[Flask](http://flask.pocoo.org/) is the only required dependency.

```bash
$ pip install -r requirements.txt
```

