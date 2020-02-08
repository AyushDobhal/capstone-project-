# capstone-project-
Capstone project 
Install
This repository contains Smart Contract code in Solidity (using Truffle), tests (also using Truffle), dApp scaffolding (using HTML, CSS and JS).

To install, download or clone the repo, then:

npm install

Start Ganache like below .
ganache-cli

In a separate terminal window,from inside the directory eth-contracts/ Compile smart contracts:

truffle.cmd compile

This will create the smart contract artifacts in folder build\contracts.

Then compile and deploy with truffle.

truffle.cmd migrate --network development --reset --compile-all

Testing
To run truffle tests from inside the directory eth-contracts/:

truffle.cmd test

Testing

Deployment
Create an account in Infura
Create a project in Infura and get the Address for deploying in Rinkeby test network
Copy the endpoint address and update the Rinkeby network information with the mnemonic and endpoint address in Truffle.js file
Fund the metamask wallet by posting a tweet in https://faucet.rinkeby.io. The post should have the address “ Requesting faucet funds into ……. On the Rinkeby Ethereum test network” Then copy the tweet in the above website and click Give me Ether.
Then deploy it using truffle.cmd deploy - -network rinkeby. If needed to deploy again use truffle.cmd migrate - -network rinkeby - - reset - -compile-all
Create ZK-Snarks Proof using Zokrates
Install Docker Community Edition here (https://docs.docker.com/install/). Virtualization should be enabled for Docker to work.

Run Zokrates docker container : docker run -v :/home/zokrates/code -ti zokrates/zokrates:0.3.0 /bin/bash

Change directory cd code/zokrates/code/square/

Compile the program written in ZoKrates DSL /path/to/zokrates compile -i square.code

Generate the Trusted Setup Now take the 'flattened' code, which is a circuit and go through a 'trusted setup' Repeat this process, every-time the program.code changes Two keys are generated - 'proving.key' and 'verification.key'

/path/to/zokrates setup

Compute Witness Having gone through the 'trusted setup' let's compute our 'witness' who knows the answer and it generates a witness file with computation steps
/path/to/zokrates compute-witness -a 3 9

Generate Proof Next step is to 'generate our proof' based on the above 'witness'. A proof.json file is generated in this step
/path/to/zokrates generate-proof

Export Verifier Last but never the least, let's generate our 'verifier' smart contract
path/to/zokrates export-verifier

Minting a Token
In a separate terminal window, launch the DApp:

npm run dev

To view dapp

http://localhost:3000

Dapp page

Storefront
Storefront is created in OpenSea marketplace https://rinkeby.opensea.io/get-listed/step-two

Properties for which tokens are minted can be viewed using e.g to view the property with token 7 https://rinkeby.opensea.io/assets/0x060A7bb346046d36d9Dc2a5154b27A1774D014A3/7

Project Notes and Links
contract address(SolnSquareVerifier): 0x060A7bb346046d36d9Dc2a5154b27A1774D014A3

contract address(SquareVerifier): 0x3Afa0Dc0b2071a56e37496c8Cf1F108BBd546666

The contract ABIs are located in the corresponding .json files under the folder build/contracts

StoreFront: https://rinkeby.opensea.io/assets/realestateonblockchain

Storefront1


Storefront

Project Resources
Remix - Solidity IDE
Visual Studio Code
Truffle Framework
Ganache - One Click Blockchain
Open Zeppelin
Interactive zero knowledge 3-colorability demonstration
Docker
ZoKrates
