# eth-Blockchain

## truffle & ganache
`npm install -g truffle`

`npm install -g ganache-cli`

`npm install solc`

## Hello World Voting
'cd hello_world_voting'

$ node

> Web3 = require('web3')'
> web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"))

> web3.eth.accounts'

> code = fs.readFileSync('Voting.sol').toString()
> solc = require('solc')
> compiledCode = solc.compile(code)

## Deploy Contract

> abiDefinition = JSON.parse(compiledCode.contracts[':Voting'].interface)

> VotingContract = web3.eth.contract(abiDefinition)

> byteCode = compiledCode.contracts[':Voting'].bytecode

> deployedContract = VotingContract.new(['Rama','Nick','Jose'],{data: byteCode, from: web3.eth.accounts[0], gas: 4700000})

> deployedContract.address

> contractInstance = VotingContract.at(deployedContract.address)

## Interact with Contract

> contractInstance.totalVotesFor.call('Rama')

> contractInstance.voteForCandidate('Rama', {from: web3.eth.accounts[0]})

> contractInstance.voteForCandidate('Rama', {from: web3.eth.accounts[0]})

> contractInstance.voteForCandidate('Rama', {from: web3.eth.accounts[0]})

> contractInstance.totalVotesFor.call('Rama').toLocaleString()

