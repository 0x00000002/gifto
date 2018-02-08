
| Contract |               Function                | Visibility | Constant |  Returns  |                Modifiers                |
|----------|---------------------------------------|------------|----------|-----------|-----------------------------------------|
| Gifto    | ()                                    | public     | false    |           | payable                                 |
| Gifto    | buyGifto()                            | public     | false    |           | payable,onSale,validValue,validInvestor |
| Gifto    | Gifto()                               | public     | false    |           |                                         |
| Gifto    | totalSupply()                         | public     | true     | uint256   |                                         |
| Gifto    | turnOnSale()                          | public     | false    |           | onlyOwner                               |
| Gifto    | turnOffSale()                         | public     | false    |           | onlyOwner                               |
| Gifto    | turnOnTradable()                      | public     | false    |           | onlyOwner                               |
| Gifto    | setIcoPercent(uint256)                | public     | false    |           | onlyOwner                               |
| Gifto    | setMaximumBuy(uint256)                | public     | false    |           | onlyOwner                               |
| Gifto    | setBuyPrice(uint256)                  | public     | false    |           | onlyOwner                               |
| Gifto    | balanceOf(address)                    | public     | true     | uint256   |                                         |
| Gifto    | isApprovedInvestor(address)           | public     | true     | bool      |                                         |
| Gifto    | getDeposit(address)                   | public     | true     | uint256   |                                         |
| Gifto    | addInvestorList(address)              | public     | false    |           | onlyOwner                               |
| Gifto    | removeInvestorList(address)           | public     | false    |           | onlyOwner                               |
| Gifto    | transfer(address,uint256)             | public     | false    | bool      | isTradable                              |
| Gifto    | transferFrom(address,address,uint256) | public     | false    | success   | isTradable                              |
| Gifto    | approve(address,uint256)              | public     | false    | success   | isTradable                              |
| Gifto    | allowance(address,address)            | public     | true     | remaining |                                         |
| Gifto    | withdraw()                            | public     | false    | bool      | onlyOwner                               |



|    Contract    |                Function                | Visibility | Constant |     Returns     |                       Modifiers                       |
|----------------|----------------------------------------|------------|----------|-----------------|-------------------------------------------------------|
| MultiSigWallet | ()                                     | public     | false    |                 | payable                                               |
| MultiSigWallet | MultiSigWallet(address,uint)           | public     | false    |                 | validRequirement                                      |
| MultiSigWallet | addOwner(address)                      | public     | false    |                 | onlyWallet,ownerDoesNotExist,notNull,validRequirement |
| MultiSigWallet | removeOwner(address)                   | public     | false    |                 | onlyWallet,ownerExists                                |
| MultiSigWallet | replaceOwner(address,address)          | public     | false    |                 | onlyWallet,ownerExists,ownerDoesNotExist              |
| MultiSigWallet | changeRequirement(uint)                | public     | false    |                 | onlyWallet,validRequirement                           |
| MultiSigWallet | submitTransaction(address,uint,bytes)  | public     | false    | transactionId   |                                                       |
| MultiSigWallet | confirmTransaction(uint)               | public     | false    |                 | ownerExists,transactionExists,notConfirmed            |
| MultiSigWallet | revokeConfirmation(uint)               | public     | false    |                 | ownerExists,confirmed,notExecuted                     |
| MultiSigWallet | executeTransaction(uint)               | public     | false    |                 | notExecuted                                           |
| MultiSigWallet | isConfirmed(uint)                      | public     | true     | bool            |                                                       |
| MultiSigWallet | addTransaction(address,uint,bytes)     | internal   | false    | transactionId   | notNull                                               |
| MultiSigWallet | getConfirmationCount(uint)             | public     | true     | count           |                                                       |
| MultiSigWallet | getTransactionCount(bool,bool)         | public     | true     | count           |                                                       |
| MultiSigWallet | getOwners()                            | public     | true     |                 |                                                       |
| MultiSigWallet | getConfirmations(uint)                 | public     | true     | _confirmations  |                                                       |
| MultiSigWallet | getTransactionIds(uint,uint,bool,bool) | public     | true     | _transactionIds |                                                       |
| MultiSigWallet | createCoin()                           | external   | false    |                 | onlyWallet                                            |
