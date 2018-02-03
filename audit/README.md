# Gifto Smart Contract Audit Report
<br>

## Preamble
This audit report was undertaken by BlockchainLabs.nz for the purpose of providing feedback to Gifto Limited. It has subsequently been shared publicly without any express or implied warranty.

Solidity contracts were sourced from the public Github repo [github.com/gifto-io/GiftoSmartContract](https://github.com/gifto-io/GiftoSmartContract) prior to commit [cf1ca1e108b3b616691761c52410756de437cb67](https://github.com/gifto-io/GiftoSmartContract/commit/cf1ca1e108b3b616691761c52410756de437cb67) - we would encourage all community members and token holders to make their own assessment of the contracts.

<br>

## Scope
All Solidity code contained in [/GiftoSmartContract](https://github.com/gifto-io/GiftoSmartContract) was considered in scope as a basis for static and dynamic analysis. The scope is outlined in the [work paper](https://github.com/tikonoff/gifto/blob/master/audit/Work_paper.MD).

<br>

## Focus Areas
The audit report is focused on the following key areas - though this is not an exhaustive list.
### Correctness
- No correctness defects uncovered during static analysis?
- No implemented contract violations uncovered during execution?
- No other generic incorrect behaviour detected during execution?
- Adherence to adopted standards such as ERC20?
### Testability
- Test coverage across all functions and events?
- Test cases for both expected behaviour and failure modes?
- Settings for easy testing of a range of parameters?
- No reliance on nested callback functions or console logs?
- Avoidance of test scenarios calling other test scenarios?
### Security
- No presence of known security weaknesses?
- No funds at risk of malicious attempts to withdraw/transfer?
- No funds at risk of control fraud?
- Prevention of Integer Overflow or Underflow?
### Best Practice
- Explicit labeling for the visibility of functions and state variables?
- Proper management of gas limits and nested execution?
- Latest version of the Solidity compiler?

<br>


## Classification
### Defect Severity
- Minor - A defect that does not have a material impact on the contract execution and is likely to be subjective.
- Moderate - A defect that could impact the desired outcome of the contract execution in a specific scenario.
- Major - A defect that impacts the desired outcome of the contract execution or introduces a weakness that may be exploited.
- Critical - A defect that presents a significant security vulnerability or failure of the contract across a range of scenarios.

<br>


## Findings
### Minor
<!--- **Tokens are not automatically transferred to investors** - `Best practice` To receive a token, the investor must `buyGifto`, and then the owner of the contract must run the `deliveryToken` function to send the investor tokens. This is a manual process so there is no guarantee for the investor that they will receive their tokens other than trust. [View on GitHub](https://github.com/BlockchainLabsNZ/gifto-contracts/issues/12)

- **Removal of setMinimumBuy without removing relevant variables** - `Best practice` We would recommend that if the intention is not to make use of the removed function setMinimumBuy, that you remove these unused variables. [View on GitHub](https://github.com/BlockchainLabsNZ/gifto-contracts/issues/16)

- **The 'onlyNotOwner' modifier is not used in the contracts** - `Best practice` There is a modifier `onlyNotOwner` which is not used by any function, this can be removed. [View on GitHub](https://github.com/BlockchainLabsNZ/gifto-contracts/issues/13)

- **Explicitly declare your variable types** - `Best practice` `uint` will default to `uint256` but it is recommended to explicitly declare it as `uint256`  [View on GitHub](https://github.com/BlockchainLabsNZ/gifto-contracts/issues/9)

- **Explicitly declare your variables access modifiers** - `Best practice` You should explicitly declare `public` on the variables that are meant to be `public`. This can help to avoid errors, but it can also cause unexpected behaviour.  [View on GitHub](https://github.com/BlockchainLabsNZ/gifto-contracts/issues/8)

- **Format repository to follow standard convention (add folders, separate files)** - `Best practice` We strongly recommend restructuring the files in your repo to follow conventional approach of other token launches. This is so that relevant files can be more easily found and increases trransparency See here for examples:    [View on GitHub](https://github.com/BlockchainLabsNZ/gifto-contracts/issues/1)
-->

- **[Misleading comments](https://github.com/tikonoff/gifto/issues/2)** - `Best practice` - Lines: [220](https://github.com/gifto-io/GiftoSmartContract/blob/cf1ca1e108b3b616691761c52410756de437cb67/Gifto.sol#L220)
- **[Folder structure has missed](https://github.com/tikonoff/gifto/issues/)** - `Best practice` - **[Old files are presented](https://github.com/tikonoff/gifto/issues/3)** - `Testability` - Lines: [xxx]()
- **[No "view" or "pure" modifiers](https://github.com/tikonoff/gifto/issues/4)** - `Best practice`,`Correctness` - Lines: [230](https://github.com/gifto-io/GiftoSmartContract/blob/cf1ca1e108b3b616691761c52410756de437cb67/Gifto.sol#L230), [239](https://github.com/gifto-io/GiftoSmartContract/blob/cf1ca1e108b3b616691761c52410756de437cb67/Gifto.sol#L239), [249](https://github.com/gifto-io/GiftoSmartContract/blob/cf1ca1e108b3b616691761c52410756de437cb67/Gifto.sol#L249)
- **[Declaration shadows a builtin symbols](https://github.com/tikonoff/gifto/issues/6)** - `Testability` - Line: [579](https://github.com/gifto-io/GiftoSmartContract/blob/cf1ca1e108b3b616691761c52410756de437cb67/Gifto.sol#L579)
- **[Implicit storage declaration](https://github.com/tikonoff/gifto/issues/7)** - `Correctness` - Line: [579](https://github.com/gifto-io/GiftoSmartContract/blob/cf1ca1e108b3b616691761c52410756de437cb67/Gifto.sol#L579)
- **[Push instead pull for internal call](https://github.com/tikonoff/gifto/issues/8)** - `Correctness` - Line: [155](https://github.com/gifto-io/GiftoSmartContract/blob/cf1ca1e108b3b616691761c52410756de437cb67/Gifto.sol#L155)


### Moderate
- **[No SafeMath Library used](https://github.com/tikonoff/gifto/issues/5)** `Best practice`, `Correctness`
  
### Major
- **[Race Condition is possible](https://github.com/tikonoff/gifto/issues/1)** - `Best practice`,`Security` 


### Critical
- None found

<br>

## Dynamic Analysis
Coverage: ???%

[Coverage screenshot]


Build: [travis-ci.org/gabriel-canaan/gifto/builds/1234](https://travis-ci.org/)

## Gas Consumption

Upon finalization of the contracts to be used by Gifto, the contracts were assessed on the gas usage of each function to ensure there aren't any unforeseen issues with exceeding the block size GasLimit. A detailed report can be found in [./Gas_Consumption.md](https://github.com/tikonoff/gifto/blob/master/audit/Gas_consumption_report.md).


## Functional tests

Functions were tested according the business scenario and available here [./kovan-functional-tests.md](https://github.com/tikonoff/gifto/blob/master/audit/kovan-functional-tests.md)


## Conclusion
Of the issues we have raised all of them are minor. 
This crowdsale has a low risk of ethereum being hacked or stolen.
