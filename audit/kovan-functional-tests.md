# Functional tests
Tests are conducted on the Kovan test network, February 5 - 9, 2018, @Bruce Li

<br>

# Gifto.sol [0x52E268](https://kovan.etherscan.io/address/0x52E268d6e557A0Ac0D5bA947879776116f57723D)

### Contract owner can:

* Start Sale period when deploy the contract
* Pause/unpause Sales during Sale period
* Turn on tradable
* Set purchasing price, ICO percent, maximum buying amount
* Add/remove a new investor to/from the investor list
* Transfer an investor's tokens to others
* Withdraw ether in the contract

### Investor can:

* Buy Gifto tokens with ETH
* Transfer their own tokens to others
* Set allowance for his own account to withdraw a specific amount of tokens and transfer to spender's account
* Withdraw tokens from another investor's account under his allowance

### Stranger can:

* Check balance of any account
* Check ETH deposit of any investor
* Check allowance of any account

<br>

## Periods
* Sales starts when the contract being deployed
* Pause/unpause sales are totally controled manually by the contract owner

<br>

## Accounts

* Contract owner [0x00812974cb8afa7fFA5081922C0f46B5a82cEA28](https://kovan.etherscan.io/address/0x00812974cb8afa7fFA5081922C0f46B5a82cEA28)

* Investor [0x0089E6eb5786e7dB31f3e2521313a502fA9596d3](https://kovan.etherscan.io/address/0x0089E6eb5786e7dB31f3e2521313a502fA9596d3)

* Stranger - Non-investor [0x006b942E2Eb0981AB083F7c680c3E43Ca5Fd7bDb](https://kovan.etherscan.io/address/0x006b942E2Eb0981AB083F7c680c3E43Ca5Fd7bDb)

<br>

## Expected behaviour tests

### Contract owner
 - [x] Contract created and deployed[0x75e9a2](https://kovan.etherscan.io/tx/0x75e9a21c1bfa45fff74332e3d30d782b370c254f6a2c713c92c02b2b07956325) 
 - [x] Pause Sales during Sale period [0x88b5ad](https://kovan.etherscan.io/tx/0x88b5ad5145a84744c70269a0fe06680bbba044b1de28390c3b4564448dfb1975)
 - [x] Unpause sales during sale period [0xc5d3c6](https://kovan.etherscan.io/tx/0xc5d3c604ff9d9d77a7f154b5d583f0fb0d6e6d91323b23a46ea4fafcac56845d)
 - [x] Start tradable period [0xc81211](https://kovan.etherscan.io/tx/0xc81211612c8b5614e875be14c8a02ab48601ca86501b00f46e50f7ac9191cc6e)
 - [x] Set perchase price [0xb93487](https://kovan.etherscan.io/tx/0xb934875bf608b85a6f2a62eea3bcdb3e09f48dff2968e9e27573591a8df3f57f)
 - [x] Set ICO percentage [0x6843f3](https://kovan.etherscan.io/tx/0x6843f39765dc2bb37c6fb7bb64dd83564cd9c73f4b4ff853ade6899e2e2a6f0f) 
 - [x] Set maximum buying amount [0x580e8d](https://kovan.etherscan.io/tx/0x580e8d2ebb8dfff62ff22fd77f715727882a9dcbcd8737aa0d036e95ffb3bf98)
 - [x] Add investor [0x0ea900](https://kovan.etherscan.io/tx/0x0ea90040b32bd6f500e0f467e9a1972754edce1b103ddd2433edcc1f76793633)
 - [x] Remove investor [0x60c3cc](https://kovan.etherscan.io/tx/0x60c3cc9a287e72a57950e0e499a17edeb4ada67d010cf39af4d9ce1db5fb55b3)
 <!-- - [x] Withdraw ether in the contract.[0x5c16b1](https://kovan.etherscan.io/tx/0x5c16b12c6c9c89a5e6f17228479436e1809513d5f643e32a31f36806bc6ca076) -->

### Investor
 - [x] Buy Gifto tokens [0x88dc1d](https://kovan.etherscan.io/tx/0x88dc1d0890512f8d825cd4634b6277c98beffa2dee32a352491d809421120d20)
 - [x] Transfer their tokens to some one else [0x2a2935](https://kovan.etherscan.io/tx/0x2a293534127fe212a137dfaf063ab17c174b78c9d43edd2c9001d7865c5296f0)
 - [x] Approve allowance [0x88f15c](https://kovan.etherscan.io/tx/0x88f15cf4ba931888a4c2a713e67ccb231b6d0876fe26319dbafaa629ffe84657)
 - [x] Withdraw tokens from another investor's account under his allowance [0xd68b59](https://kovan.etherscan.io/tx/0xd68b5995129002c6804e2c1114ca0566cfcb7b89a913d035977cbe395f3ac05c)
 
### Stranger
 - [x] Check balance of any account
 - [x] Check ETH deposit of any investor
 - [x] Check allowance of any account

<br>

## Unexpected behaviour tests (reverted)

### Contract owner
 - [ ] Turn on sales when it is already on.[0x06a246](https://kovan.etherscan.io/tx/0x06a246d6e7cecc2d9223dea578472431b0ffec77f9c8c6d3810f14aa23b67d5c)
<font color="#ff0000">Suggest to verify the variable status before turn it on. Or you just lose your gas if it is already on.</font>
 - [ ] Turn off sales when it is already off.[0x06a246](https://kovan.etherscan.io/tx/0x06a246d6e7cecc2d9223dea578472431b0ffec77f9c8c6d3810f14aa23b67d5c)
 **Suggest to verify the variable status before turn it off. Or you just lose your gas if it is already off.**
 - [x] Transfer tokens from one investor to another without enough allowance. [0xf8df16](https://kovan.etherscan.io/tx/0xf8df16329984d6906d0bee6086e29fbe11b4d0ed6f78e482d226065099692637)

### Investor
 - [x] Turn on tradable.[0x2daa90](https://kovan.etherscan.io/tx/0x2daa906870f9a11888a061d9c46502cc19ef5f0b8eb3d7592f8a38bdf569f47b)
 - [x] Pause Sales during Sale period [0x88b5ad](https://kovan.etherscan.io/tx/0x88b5ad5145a84744c70269a0fe06680bbba044b1de28390c3b4564448dfb1975)
 - [x] Unpause sales during sale period [0x169752](https://kovan.etherscan.io/tx/0x1697529ff793cb2085862e8dacca768fbe38d27f73ce12a598611987c8e69703)
 - [x] Set purchasing price.[0x610063](https://kovan.etherscan.io/tx/0x6100631b332ed6e3cef73b9270c3fd9de97b0ee822b6a082964bbbac5631fde8)
 - [x] Set ICO percent.[0xf1bf4e](https://kovan.etherscan.io/tx/0xf1bf4e78c5cd8da10d78cc43d242b60fc5d05739ac693273392ffcf1bdaa6136)
 - [x] Set maximum buying amount.[0xc8b4c0](https://kovan.etherscan.io/tx/0xc8b4c0cef33164ac23e27426725acdc35d896def81c4267cfcb60eea07d4c96f)
 - [x] Add a new investor to the investor list.[0x95f150](https://kovan.etherscan.io/tx/0x95f150e73cd672ee8ab7228004e95cd3f0c14da5f52ad0d02b4ee3b452adeac2)
 - [x] Remove investor from the investor list.[0x32a56c](https://kovan.etherscan.io/tx/0x32a56c2d1a4e23f1b51371d7fc390f9f5333c2e9985c29b65a1d4c01ef498fb4)
 - [x] Transfer an investor's tokens to others.[0x1c7e88](https://kovan.etherscan.io/tx/0x1c7e88c955220d6b8daf456af63f0c28153c88284b4650c94c3576348ff22b47)


### Stranger
 - [x] Turn on tradable.[0xe7e466](https://kovan.etherscan.io/tx/0xe7e4665c1278ea73a1c0aabef70f43d1279fdf86dd3d8df15e461e82c4654d3f)
 - [x] Pause Sales during sale period [0x040e21](https://kovan.etherscan.io/tx/0x040e21f8fcf818ab19b8e7821d113ad18cf4a9d25182c060b8785f369a6e3946)
 - [x] Unpause sales during sale period [0x921f91](https://kovan.etherscan.io/tx/0x921f915149f37750d7193627cb6aad822fbeeae0eb326af12b5cfe0d7c21de62)
 - [x] Set purchasing price.[0x48c19b](https://kovan.etherscan.io/tx/0x48c19b1572f2868e9f21aa9d949e59b8cb0c19d69e4687868ca0412b46fa3573)
 - [x] Set ICO percent.[0xd95686](https://kovan.etherscan.io/tx/0xd956863981e5bfb3b8921e15eb4e51fd7e76910ad5c231a2bcf4402168a636f2)
 - [x] Set maximum buying amount.[0x6d6806](https://kovan.etherscan.io/tx/0x6d680665693d1e5d0e3b977c1d594bc425a483f3024503f39ebbf6c438b2a172)
 - [x] Add a new investor to the investor list.[0xda6208](https://kovan.etherscan.io/tx/0xda62086f5c48660a87c2e31b8e00c83dabb236050b0dbbddffc6b3bf3c1a109c)
 - [x] Remove an investor from the investor list.[0x6fe688](https://kovan.etherscan.io/tx/0x6fe688222cf80c2ab6131d085728ca21bf2549203cfa475a683a158ceb2423c3)
 - [x] Transfer an investor's tokens to others.[0xe5c347](https://kovan.etherscan.io/tx/0xe5c3476c3bcccb06c04163e88f4cd502369e7bbedea9eeb806cf538393a5c09a)
 - [x] Buy Gifto tokens with ETH.[0x44459a](https://kovan.etherscan.io/tx/0x44459ab7af839d2bb5234287c63c1b8b96d671bea2c5223bae69c42eb767f8aa)
 - [x] Transfer their own tokens to others.[0xf73ec8](https://kovan.etherscan.io/tx/0xf73ec878e9941567e17457c7585e2656babefec0db4ad2bd54da697222f557b6)
 - [ ] Set allowance to a specific spender for his own account so that the spender can withdraw tokens under this allowance and transfer to spender's account.[0xc03dba](https://kovan.etherscan.io/tx/0xc03dbacddd3cb4279331b4bc1996e3f596123a0f2fdda8b80f4ec28b3bea44a9) **Suggest only allow investor to do this action.**
 - [ ] Withdraw tokens from another investor's account under his allowance.[0x1e5d97](https://kovan.etherscan.io/tx/0x1e5d97002d2cc2e1a139f7f36239959d68e717b35f198ca65376f1b59cabf135) **Suggest only allow investor to do this action.**
