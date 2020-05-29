# Transactions

A collection of Ethereum transaction data and it is being updated in \(close to\) real time. Let's take a look at its attributes first:

* **blockNumber and blockTimestamp:** The block number and the time when this transaction happened. BlockTimestamp is in UTC format.
* **transactionHash:** The unique identification of a transaction.
* **from:** The party that initiated this transaction. It is always an [Externally Owned Account](https://ethdocs.org/en/latest/contracts-and-transactions/account-types-gas-and-transactions.html), commonly known as a wallet address.
* **function:** The smart contract function that was executed in this transaction. This is one of the key elements to track protocol/dApp metrics. Only one function can be executed in a transaction. The **function** is an object type and it also contains a few child attributes: 
  * **name:** The name of a function. Different smart contracts can have the exact same function name. For example, every ERC20 token contract has a function called "transfer". To identify a unique function, it's best to use both the name and the **contractAddress** attribute**.**
  * **methodId:** This is a value encoded based on the name and parameters of a function. The uniqueness is also not guaranteed. You can check out the technical definition [here](https://web3js.readthedocs.io/en/v1.2.0/web3-eth-abi.html#encodefunctionsignature). It is possible to 
  * **params:** these are the inputs of a function. 
* **logs:** This is another key element to track dApp/protocol metrics. Smart contract developers typically put logs when a smart contract function is executed, it normally leaves some footprints. One transaction can have multiple logs.

{% hint style="info" %}
A smart contract contains functions and logs. Let's use [RebalanceAuctionModule](https://github.com/SetProtocol/set-protocol-contracts/blob/master/contracts/core/modules/RebalanceAuctionModule.sol) smart contract as an example. In this contract, you can find the below code snippet: 

```text
function bidAndWithdraw(
     address _rebalancingSetToken,
     uint256 _quantity,
     bool _allowPartialFill
)
```

This is a smart contract function called _bidAndWithdraw_. When a set portfolio rebalance is initiated on Set Protocol, this is one of the functions that is executed in a blockchain transaction. In that transaction, you will find the value of the **function** attribute ****is _bidAndWithdraw_.  

Now, let's look at the **logs** attribute. Below is the definition of a log you can find in the smart contract.

```text
emit BidPlaced(
     _rebalancingSetToken,
     msg.sender,
     executionQuantity,
     tokenArray,
     inflowUnitArray,
     outflowUnitArray
)
```

There are multiple logs in a transaction.
{% endhint %}

* **status:** It has two values. If the transaction was successful, the value is true; If not, the value is false.
* **gasPrice:** The price of the gas when the transaction was executed. The unit is in Wei.



