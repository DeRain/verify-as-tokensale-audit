# Manual audit of the code

## CREDToken.sol

| Lines      | Code sample                                                     | Issue                                                                                                                                                                                  | Priority |
|------------|-----------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| 27, 28, 29 | address public teamWallet;                                      | Wallets is not a part of the ERC20 token contract                                                                                                                                      | Low      |
| 35, 36, 37 | uint256 teamLocked;                                             | Token locked values is not a part of the ERC20 token contract                                                                                                                          | Low      |
| 47         | TokenVesting public advisorsVesting = TokenVesting(address(0)); | Assignment does make no sense without proper arguments for TokenVesting                                                                                                                | Low      |
| 65         | modifier mintLockedOnlyOnce {                                   | Unused modifier                                                                                                                                                                        | Low      |
| 83-97      | function CREDToken(                                             | Wallets is not a part of the ERC20 token contract                                                                                                                                      | Low      |
| 130        | owner = 0;                                                      | Scheme without owner could leads to the tokens lost. Use this only if necessary.                                                                                                       | Medium   |
| 138        | function unfreeze() public                                      | Possible you don't want to allow to call this method by anyone. Using timestamp dependence and allowance to call this method to anyone could lead to attack by timestamp manipulation. | High     |
| 154        | function unlockAdvisorTokens() public whenLiquid {              | Possible you don't want to allow to call this method by anyone. Using timestamp dependence and allowance to call this method to anyone could lead to attack by timestamp manipulation. | High     |


## Tokensale.sol
