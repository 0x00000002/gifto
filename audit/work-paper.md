# Work paper

performed Feb 8, 2019 by [tikonoff](https://github.com/tikonoff)


## Gifto
| Contract |               Function                | Visibility | Constant |  Returns  |                Modifiers                |              Static Analysis              |   Test Coverage    | Functional Analysis |
|----------|---------------------------------------|------------|----------|-----------|-----------------------------------------|-------------------------------------------|--------------------|---------------------|
| Gifto    | ()                                    | public     | false    |           | payable                                 | :white_check_mark: | :white_check_mark: |                     |
| Gifto    | buyGifto()                            | public     | false    |           | payable,onSale,validValue,validInvestor | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | Gifto()                               | public     | false    |           |                                         | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | totalSupply()                         | public     | true     | uint256   |                                         | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | turnOnSale()                          | public     | false    |           | onlyOwner                               | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | turnOffSale()                         | public     | false    |           | onlyOwner                               | :white_check_mark: |                    | :white_check_mark:  |
| Gifto    | turnOnTradable()                      | public     | false    |           | onlyOwner                               | :white_check_mark: |                    | :white_check_mark:  |
| Gifto    | setIcoPercent(uint256)                | public     | false    |           | onlyOwner                               | :white_check_mark: |                    | :white_check_mark:  |
| Gifto    | setMaximumBuy(uint256)                | public     | false    |           | onlyOwner                               | :white_check_mark: |                    | :white_check_mark:  |
| Gifto    | setBuyPrice(uint256)                  | public     | false    |           | onlyOwner                               | :white_check_mark: |                    | :white_check_mark:  |
| Gifto    | balanceOf(address)                    | public     | true     | uint256   |                                         | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | isApprovedInvestor(address)           | public     | true     | bool      |                                         | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | getDeposit(address)                   | public     | true     | uint256   |                                         | :white_check_mark: |                    | :white_check_mark:  |
| Gifto    | addInvestorList(address)              | public     | false    |           | onlyOwner                               | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | removeInvestorList(address)           | public     | false    |           | onlyOwner                               | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | transfer(address,uint256)             | public     | false    | bool      | isTradable                              | :white_check_mark: | :white_check_mark: |                     |
| Gifto    | transferFrom(address,address,uint256) | public     | false    | success   | isTradable                              | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | approve(address,uint256)              | public     | false    | success   | isTradable                              | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| Gifto    | allowance(address,address)            | public     | true     | remaining |                                         | :white_check_mark: |                    | :white_check_mark:  |
| Gifto    | withdraw()                            | public     | false    | bool      | onlyOwner                               | :white_check_mark: | :white_check_mark: |                     |


## MultiSigWallet



|    Contract    |                Function                | Visibility | Constant |     Returns     |                       Modifiers                       |              Static Analysis              |   Test Coverage    | Functional Analysis |
|----------------|----------------------------------------|------------|----------|-----------------|-------------------------------------------------------|-------------------------------------------|--------------------|---------------------|
| MultiSigWallet | ()                                     | public     | false    |                 | payable                                               | :white_check_mark: | :white_check_mark: |                     |
| MultiSigWallet | MultiSigWallet(address,uint)           | public     | false    |                 | validRequirement                                      | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | addOwner(address)                      | public     | false    |                 | onlyWallet,ownerDoesNotExist,notNull,validRequirement | :white_check_mark: |                    |                     |
| MultiSigWallet | removeOwner(address)                   | public     | false    |                 | onlyWallet,ownerExists                                | :white_check_mark: |                    |                     |
| MultiSigWallet | replaceOwner(address,address)          | public     | false    |                 | onlyWallet,ownerExists,ownerDoesNotExist              | :white_check_mark: |                    |                     |
| MultiSigWallet | changeRequirement(uint)                | public     | false    |                 | onlyWallet,validRequirement                           | :white_check_mark: |                    |                     |
| MultiSigWallet | submitTransaction(address,uint,bytes)  | public     | false    | transactionId   |                                                       | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | confirmTransaction(uint)               | public     | false    |                 | ownerExists,transactionExists,notConfirmed            | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | revokeConfirmation(uint)               | public     | false    |                 | ownerExists,confirmed,notExecuted                     | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | executeTransaction(uint)               | public     | false    |                 | notExecuted                                           | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | isConfirmed(uint)                      | public     | true     | bool            |                                                       | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | addTransaction(address,uint,bytes)     | internal   | false    | transactionId   | notNull                                               | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | getConfirmationCount(uint)             | public     | true     | count           |                                                       | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | getTransactionCount(bool,bool)         | public     | true     | count           |                                                       | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | getOwners()                            | public     | true     |                 |                                                       | :white_check_mark: | :white_check_mark: | :white_check_mark:  |
| MultiSigWallet | getConfirmations(uint)                 | public     | true     | _confirmations  |                                                       | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | getTransactionIds(uint,uint,bool,bool) | public     | true     | _transactionIds |                                                       | :white_check_mark: |                    | :white_check_mark:  |
| MultiSigWallet | createCoin()                           | external   | false    |                 | onlyWallet                                            | :white_check_mark: |                    | :white_check_mark:  |

