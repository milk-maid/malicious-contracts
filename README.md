# Sample Hardhat Project

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, and a script that deploys that contract.

Try running some of the following tasks:

```shell
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat run scripts/deploy.js
```

Malicious.sol is that it will generate the same ABI as Helper.sol even though it has different code within it. This is because ABI only contains function definitions for public variables, functions and events. So Malicious.sol can be typecasted as Helper.sol.

Now because Malicious.sol can be typecasted as Helper.sol, a malicious owner can deploy Good.sol with the address of Malicious.sol instead of Helper.sol and users will believe that he is indeed using Helper.sol to create the eligibility list.

Prevention

Make the address of the external contract public and also get your external contract verified so that all users can view the code
Create a new contract, instead of typecasting an address into a contract inside the constructor. So instead of doing Helper(_helper ) where you are typecasting (_helper) address into a contract which may or may not be the Helper contract, create an explicit new helper contract instance using new Helper() ... for instance

```solidity
contract Good {
    Helper public helper;
    constructor() {
        helper = new Helper();
    }
}```
