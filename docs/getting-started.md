# Getting Started

## Install dependencies

- Use nodejs v8.12: `nvm install 8.12 && nvm alias default 8.12`
- Install local dependencies: `npm install`

## Node

You need a node to run contracts. Ganache cli for developing purpose

1. Ganache-cli

- Globally:

```sh
npm install -g ganache-cli;
npm run ganache-cli
```

- Using Docker:

```sh
docker pull trufflesuite/ganache-cli;
docker run -d -p 8545:8545 trufflesuite/ganache-cli:latest
```

2. Rsk Local Node

- With Docker:
  See this repo: https://github.com/rsksmart/artifacts/tree/master/Dockerfiles/RSK-Node

## Tests

**Node**

Before running any test, run Ganache using this command:
- run Ganache node: `npm run ganache-cli`

**Tests**

Once you have Ganache running
- run: `npm run test`

_NOTE:_ if you need accounts with a balance greater than 1M ether for running your tests, stop your Ganache instance and run only `npm run test`

It will launch another Ganache instance with 11 accounts: the first one will have a balance of 10M ether and the remaining ones will have a balance of 1M ether each.

**Tests With Coverage**

Coverage test use their own node, so there is no need to run Ganache separately.
- run: `npm run coverage`
- browse: `./coverage/index.html` inside your project folder.

## Deploy

[Truffle suite](https://github.com/trufflesuite/truffle) is recommended to compile and deploy the contracts.

1.  Edit truffle.js and change add network changes and point to your
    ganache-cli or RSK node.

2.  Edit migrations/config/config.json and make changes

3.  Run `npm run truffle-compile` to compile the code

4.  Run `npm run migrate-development` to deploy the contracts

### Security and Audits

[Deployed Contracts](Contracts%20verification.md)
[Audits](https://github.com/money-on-chain/Audits)

For more technical information you can see our [ABI documentation](abis/README.md)
