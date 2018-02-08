# Work paper

performed Feb 8, 2019 by [tikonoff](https://github.com/tikonoff)


## Gifto
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


## MultiSigWallet


|    Contract    |                Function                | Visibility | Constant |     Returns     |                       Modifiers                       |              Static Analysis              |   Test Coverage    | Functional Analysis |
|----------------|----------------------------------------|------------|----------|-----------------|-------------------------------------------------------|-------------------------------------------|--------------------|---------------------|
| MultiSigWallet | ()                                     | public     | false    |                 | payable                                               | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | MultiSigWallet(address,uint)           | public     | false    |                 | validRequirement                                      | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | addOwner(address)                      | public     | false    |                 | onlyWallet,ownerDoesNotExist,notNull,validRequirement | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | removeOwner(address)                   | public     | false    |                 | onlyWallet,ownerExists                                | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | replaceOwner(address,address)          | public     | false    |                 | onlyWallet,ownerExists,ownerDoesNotExist              | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | changeRequirement(uint)                | public     | false    |                 | onlyWallet,validRequirement                           | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | submitTransaction(address,uint,bytes)  | public     | false    | transactionId   |                                                       | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | confirmTransaction(uint)               | public     | false    |                 | ownerExists,transactionExists,notConfirmed            | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | revokeConfirmation(uint)               | public     | false    |                 | ownerExists,confirmed,notExecuted                     | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | executeTransaction(uint)               | public     | false    |                 | notExecuted                                           | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | isConfirmed(uint)                      | public     | true     | bool            |                                                       | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | addTransaction(address,uint,bytes)     | internal   | false    | transactionId   | notNull                                               | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | getConfirmationCount(uint)             | public     | true     | count           |                                                       | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | getTransactionCount(bool,bool)         | public     | true     | count           |                                                       | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | getOwners()                            | public     | true     |                 |                                                       | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | getConfirmations(uint)                 | public     | true     | _confirmations  |                                                       | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | getTransactionIds(uint,uint,bool,bool) | public     | true     | _transactionIds |                                                       | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | createCoin()                           | external   | false    |                 | onlyWallet                                            | :white_check_mark::ballot_box_with_check: | :white_check_mark: | :white_check_mark:  |
