Simple decentralized voting app using the truffle framework and deployed to the public Ropsten testnet.

This voting app implements a shareholder style of voting where you get to vote based on the number of shares
you own in the company. 

Users can buy tokens using ethereum. Each token purchased represents one vote. Users
can vote for each candidate as many times as they can afford to based on how many tokens they have. 

Here is a diagram of the interaction between the voters and the contract.

The contract is deployed like this:

```solidiy
deployer.deploy(Voting, 1000, web3.toWei('0.1', 'ether'), ['Rama', 'Nick', 'Jose']);

// 1000 is the total number of tokens for sale and the price of each token is set to 0.1 ether.
// We will revisit this section again later in this tutorial.
```

An example buy order looks like this:

```solidiy
truffle(development)> Voting.deployed().then(function(contract) {contract.buy({value: web3.toWei('1', 'ether'), from: web3.eth.accounts[1]})})
```




![image](https://user-images.githubusercontent.com/3628956/34448051-aa9de89e-ecaf-11e7-8261-18e4b508fb8a.png)

