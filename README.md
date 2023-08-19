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
