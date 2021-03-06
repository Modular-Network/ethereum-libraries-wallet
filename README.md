WalletLib
=========================   

[![Build Status](https://travis-ci.org/Modular-Network/ethereum-libraries.svg?branch=master)](https://travis-ci.org/Modular-Network/ethereum-libraries)
[![Discord](https://img.shields.io/discord/102860784329052160.svg)](https://discord.gg/crxYSF2)   

!!!DO NOT USE, IN THE PROCESS OF UPGRADING!!!
A wallet library family [provided by Modular-Network](https://modular.network "Modular's Website") composed of 3 libraries to use for multisig wallet contract deployment.   

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Library Addresses](#library-addresses)
  - [WalletMainLib](#walletmainlib)
  - [WalletAdminLib](#walletadminlib)
  - [WalletGetterLib](#walletgetterlib)
- [License and Warranty](#license-and-warranty)
- [How to install](#how-to-install)
  - [Truffle Installation](#truffle-installation)
    - [Manual Install](#manual-install)
    - [Testing the library in truffle](#testing-the-library-in-truffle)
  - [solc Installation](#solc-installation)
    - [With standard JSON input](#with-standard-json-input)
    - [solc without standard JSON input](#solc-without-standard-json-input)
    - [solc documentation](#solc-documentation)
  - [solc-js Installation](#solc-js-installation)
    - [Solc-js Installation via Linking](#solc-js-installation-via-linking)
    - [Solc-js documentation](#solc-js-documentation)
  - [Basic Usage](#basic-usage)
  - [Usage Example](#usage-example)
- [Functions](#functions)
  - [Primary Functions](#primary-functions)
    - [init(WalletMainLib.WalletData storage, address[], uint256, uint256, uint256, uint256)](#initwalletmainlibwalletdata-storage-address-uint256-uint256-uint256-uint256)
      - [Arguments](#arguments)
      - [Returns](#returns)
    - [serveTx(WalletMainLib.WalletData, address, uint256, bytes, bool, bytes)](#servetxwalletmainlibwalletdata-address-uint256-bytes-bool-bytes)
      - [Arguments](#arguments-1)
      - [Returns](#returns-1)
    - [confirmTx(WalletMainLib.WalletData storage, bytes32)](#confirmtxwalletmainlibwalletdata-storage-bytes32)
      - [Arguments](#arguments-2)
      - [Returns](#returns-2)
    - [revokeConfirm(WalletMainLib.WalletData storage, bytes32)](#revokeconfirmwalletmainlibwalletdata-storage-bytes32)
      - [Arguments](#arguments-3)
      - [Returns](#returns-3)
  - [Administrative Functions](#administrative-functions)
    - [changeOwner(WalletMainLib.WalletData storage, address, address, bool, bytes)](#changeownerwalletmainlibwalletdata-storage-address-address-bool-bytes)
      - [Arguments](#arguments-4)
      - [Returns](#returns-4)
    - [addOwner(WalletMainLib.WalletData storage, address, bool, bytes)](#addownerwalletmainlibwalletdata-storage-address-bool-bytes)
      - [Arguments](#arguments-5)
      - [Returns](#returns-5)
    - [removeOwner(WalletMainLib.WalletData storage, address, bool, bytes)](#removeownerwalletmainlibwalletdata-storage-address-bool-bytes)
      - [Arguments](#arguments-6)
      - [Returns](#returns-6)
    - [changeRequiredAdmin(WalletMainLib.WalletData storage, uint256, bool, bytes)](#changerequiredadminwalletmainlibwalletdata-storage-uint256-bool-bytes)
      - [Arguments](#arguments-7)
      - [Returns](#returns-7)
    - [changeRequiredMajor(WalletMainLib.WalletData storage, uint256, bool, bytes)](#changerequiredmajorwalletmainlibwalletdata-storage-uint256-bool-bytes)
      - [Arguments](#arguments-8)
      - [Returns](#returns-8)
    - [changeRequiredMinor(WalletMainLib.WalletData storage, uint256, bool, bytes)](#changerequiredminorwalletmainlibwalletdata-storage-uint256-bool-bytes)
      - [Arguments](#arguments-9)
      - [Returns](#returns-9)
    - [changeMajorThreshold(WalletMainLib.WalletData storage, address, address, bool, bytes)](#changemajorthresholdwalletmainlibwalletdata-storage-address-address-bool-bytes)
      - [Arguments](#arguments-10)
      - [Returns](#returns-10)
  - [Getter Functions](#getter-functions)
    - [getOwners(WalletMainLib.WalletData storage)](#getownerswalletmainlibwalletdata-storage)
      - [Arguments](#arguments-11)
      - [Returns](#returns-11)
    - [getOwnerIndex(WalletMainLib.WalletData storage)](#getownerindexwalletmainlibwalletdata-storage)
      - [Arguments](#arguments-12)
      - [Returns](#returns-12)
    - [getMaxOwners(WalletMainLib.WalletData storage)](#getmaxownerswalletmainlibwalletdata-storage)
      - [Arguments](#arguments-13)
      - [Returns](#returns-13)
    - [getOwnerCount(WalletMainLib.WalletData storage)](#getownercountwalletmainlibwalletdata-storage)
      - [Arguments](#arguments-14)
      - [Returns](#returns-14)
    - [getRequiredAdmin(WalletMainLib.WalletData storage)](#getrequiredadminwalletmainlibwalletdata-storage)
      - [Arguments](#arguments-15)
      - [Returns](#returns-15)
    - [getRequiredMinor(WalletMainLib.WalletData storage)](#getrequiredminorwalletmainlibwalletdata-storage)
      - [Arguments](#arguments-16)
      - [Returns](#returns-16)
    - [getRequiredMajor(WalletMainLib.WalletData storage)](#getrequiredmajorwalletmainlibwalletdata-storage)
      - [Arguments](#arguments-17)
      - [Returns](#returns-17)
    - [getCurrentSpend(WalletMainLib.WalletData storage, address)](#getcurrentspendwalletmainlibwalletdata-storage-address)
      - [Arguments](#arguments-18)
      - [Returns](#returns-18)
    - [getMajorThreshold(WalletMainLib.WalletData storage, address)](#getmajorthresholdwalletmainlibwalletdata-storage-address)
      - [Arguments](#arguments-19)
      - [Returns](#returns-19)
    - [getTransactionLength(WalletMainLib.WalletData storage, bytes32)](#gettransactionlengthwalletmainlibwalletdata-storage-bytes32)
      - [Arguments](#arguments-20)
      - [Returns](#returns-20)
    - [getTransactionConfirms(WalletMainLib.WalletData storage, bytes32, uint256)](#gettransactionconfirmswalletmainlibwalletdata-storage-bytes32-uint256)
      - [Arguments](#arguments-21)
      - [Returns](#returns-21)
    - [getTransactionConfirmCount(WalletMainLib.WalletData storage, bytes32, uint256)](#gettransactionconfirmcountwalletmainlibwalletdata-storage-bytes32-uint256)
      - [Arguments](#arguments-22)
      - [Returns](#returns-22)
    - [getTransactionSuccess(WalletMainLib.WalletData storage, bytes32, uint256)](#gettransactionsuccesswalletmainlibwalletdata-storage-bytes32-uint256)
      - [Arguments](#arguments-23)
      - [Returns](#returns-23)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Library Addresses   

### WalletMainLib
**Main Ethereum Network**:     
**Rinkeby Test Network**:     

### WalletAdminLib
**Main Ethereum Network**:     
**Rinkeby Test Network**:     

### WalletGetterLib
**Main Ethereum Network**:     
**Rinkeby Test Network**:     

## License and Warranty   

Be advised that while we strive to provide professional grade, tested code we cannot guarantee its fitness for your application. This is released under [The MIT License (MIT)](https://github.com/Modular-Network/ethereum-libraries/blob/master/LICENSE "MIT License") and as such we will not be held liable for lost funds, etc. Please use your best judgment and note the following:   

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NON-INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Installation and Usage

### How to install

`npm install ethereum-libraries-wallet`

### How to link

Amend the deployment .js file in your truffle `migrations/` directory as follows:

```js
var WalletMainLib = artifacts.require("ethereum-libraries-wallet/contracts/WalletMainLib.sol");
var WalletAdminLib = artifacts.require("ethereum-libraries-wallet/contracts/WalletAdminLib.sol");
var WalletGetterLib = artifacts.require("ethereum-libraries-wallet/contracts/WalletGetterLib.sol");
var YourWalletContract = artifacts.require("./YourWalletContract.sol");
...

module.exports = function(deployer) {
  deployer.deploy(WalletMainLib, {overwrite: false});
  deployer.deploy(WalletAdminLib, {overwrite: false});
  deployer.deploy(WalletGetterLib, {overwrite: false});
  deployer.link(WalletMainLib, YourWalletContract);
  deployer.link(WalletAdminLib, YourWalletContract);
  deployer.link(WalletGetterLib, YourWalletContract);
  deployer.deploy(YourWalletContract);
};
```

**Note**: If you have not created a second deployment .js file in the `migrations/` directory, this needs to be done first. You cannot use the 1_initial_migration.js file for your migrations.   

**Note**: The `.link()` function should be called *before* you `.deploy(YourWalletContract)`. Also, be sure to include the `{overwrite: false}` when writing the deployer i.e. `.deploy(WalletMainLib, {overwrite: false})`. This prevents deploying the library onto the main network at your cost and uses the library already on the blockchain. The function should still be called however because it allows you to use it in your development environment. *See below*

### Testing

Test: `npm run test`  

Test Coverage: Solidity coverage is not currently emitting events properly for Solidity v0.4.21

### solc Installation

**version 0.4.21**

For direction and instructions on how the Solidity command line compiler works [see the documentation](https://solidity.readthedocs.io/en/develop/using-the-compiler.html#using-the-commandline-compiler "Solc CLI Doc").   

#### With standard JSON input

[The Standard JSON Input](https://solidity.readthedocs.io/en/develop/using-the-compiler.html#input-description "Standard JSON Input") provides an easy interface to include libraries. Include the following as part of your JSON input file:

```json
{
  "language": "Solidity",
  "sources":
  {
    "YourContract.sol": {
      ...
      ...
    },
    "WalletMainLib.sol": {
      "content": "[Contents of WalletMainLib.sol]"
    },
    "WalletAdminLib.sol": {
      "content": "[Contents of WalletAdminLib.sol]"
    },
    "WalletGetterLib.sol": {
      "content": "[Contents of WalletGetterLib.sol]"
    }
  },
  "settings":
  {
    ...
    "libraries": {
      "YourContract.sol": {
        "WalletMainLib": "",
        "WalletAdminLib": "",
        "WalletGetterLib": "",
      }
    }
  }
}
```

#### solc without standard JSON input

When creating unlinked binary, the compiler currently leaves special substrings in the compiled bytecode in the form of '____LibraryName____' which leaves a 20 byte space for the library's address. In order to include the deployed libraries in your bytecode create a file with one library string per line and include these libraries as follows:     

```
"WalletMainLib:"
"WalletAdminLib:"
"WalletGetterLib:"
```

then add the following flag to your command:

`--libraries filename`

Finally, if you have an unlinked binary already stored with the '____LibraryName____' placeholder, you can run the compiler with the --link flag and include each library with the following flag:

`--libraries "WalletMainLib:"`

#### solc documentation

[See the solc documentation for further information](https://solidity.readthedocs.io/en/develop/using-the-compiler.html#using-the-commandline-compiler "Solc CLI Doc").

### solc-js Installation

**version 0.4.21**

Solc-js provides javascript bindings for the Solidity compiler and [can be found here](https://github.com/ethereum/solc-js "Solc-js compiler"). Please refer to their documentation for detailed use.   

This version of Solc-js also uses the [standard JSON input](#with-standard-json-input) to compile a contract. The entry function is `compileStandardWrapper()` and you can create a standard JSON object explained under the [solc section](#with-standard-json-input) and incorporate it as follows:

```js
var solc = require('solc');
var fs = require('fs');

var file = fs.readFileSync('/path/to/YourWalletContract.sol','utf8');
var mainLib = fs.readFileSync('./path/to/WalletMainLib.sol','utf8');
var adminLib = fs.readFileSync('./path/to/WalletAdminLib.sol','utf8');
var getterLib = fs.readFileSync('./path/to/WalletGetterLib.sol','utf8');

var input = {
  "language": "Solidity",
  "sources":
  {
    "YourContract.sol": {
      "content": file
    },
    "WalletMainLib.sol": {
      "content": mainLib
    },
    "WalletAdminLib.sol": {
      "content": adminLib
    },
    "WalletGetterLib.sol": {
      "content": getterLib
    }
  },
  "settings":
  {
    ...
    "libraries": {
      "YourContract.sol": {
        "WalletMainLib": "",
        "WalletAdminLib": "",
        "WalletGetterLib": "",
      }
    }
    ...
  }
}

var output = JSON.parse(solc.compileStandardWrapper(JSON.stringify(input)));

//Where the output variable is a standard JSON output object.
```

#### Solc-js Installation via Linking

Solc-js also provides a linking method if you have compiled binary code already with the placeholder. To link each library the call would be:

```js
bytecode = solc.linkBytecode(bytecode, { 'WalletMainLib': '' });
```

#### Solc-js documentation

[See the Solc-js documentation for further information](https://github.com/ethereum/solc-js "Solc-js compiler").

### Basic Usage

The Wallet Libraries provide all of the functionality needed to generate a fully functional multisig wallet. Functionality is split into 3 different libraries. Each library serves the following purposes:

1. WalletMainLib: This is the main library used to create a wallet and initialize parameters. It contains the WalletData struct which should be placed in the storage of your wallet contract. This library also contains the primary transaction initiating, confirming, and revocation code.

2. WalletAdminLib: This library contains all of the functionality to change the parameters of your multisig wallet such as adding owners, changing signature requirements, etc.

3. WalletGetterLib: This library contains all of the getter functions for your wallet data.

The wallet generated will have some of these benefits and characteristics:

   * Can have up to 50 wallet owners.
   * Allows for signature requirements to be defined for three types of operations: administrative, minor transactions, and major transactions.   
          **Administrative:** These are transactions that change signature requirements, add owners, remove owners, etc.   
          **Minor Transactions:** These are ether or token transfers below a set daily threshold.   
          **Major Transactions:** These are ether or token transfers at or above a set daily threshold.   
   * Allows a major transaction threshold to be set individually for any token.
   * Provides a transaction hash for any pending transaction such as is implemented in Gav's wallet, allowing subsequent signatures to be submitted by hash.
   * Can create other contracts from within the wallet.
   * Any new token will automatically have a major threshold of 0 until a threshold is defined by the wallet owners.
   * Allows signatures to be revoked at any point in time prior to the transaction confirming.

The wallet contract should put the `init` function from the WalletMainLib in the constructor with the required parameters given. Once deployed, owners can initiate any transaction by calling the appropriate function with the required data for admin functions, transfer or value data for token or ether transactions, or contract data for deploying new contracts. Most transaction requests end with a `bool` and `bytes` parameter. The `bool` parameter should be true for any transaction being initiated or confirmed and false for any signature revocation. The `bytes` parameter should be the msg.data passed automatically by the wallet contract. [See our example wallet contract](https://www.github.com/Modular-Network/ethereum-contracts "Modular-Network repo") to get a better idea of its implementation.

Most functions return two parameters, a `bool` and a `bytes32`. The transaction and admin functions will generally return false and log an error event when submitted parameters are either wrong or the call will not work. In the case of a non-owner attempting to submit a transaction or any failure during actual execution, the function will throw a standard out of gas error with no reason in order to successfully revert changes. These functions will return true if any confirm or revocation call is successful. The functions that return a `bytes32` will also log this value in an event. Owners may choose to use the generic `confirmTx` or `revokeConfirm` functions by providing the id for any transaction already initiated, a concept artfully developed by Gav of York himself.

**DISCLAIMER:** As always, please ensure you review this code thoroughly for your team's use. We strive to make our code as solid, clean, and well documented as possible but will not accept liability for unforeseen circumstances in which value is lost or stolen. This includes but not limited to any inability to meet signature requirements to move funds, loss of private keys, transactions you deem unauthorized from an owner's account, a non-owners ability to gain access to your wallet, etc. The library code has been thoroughly tested by our team and believe it to be suitable enough to be posted in our open source repository, however, you are still responsible for its implementation and security in your smart contract. Please use your best judgment. Please [let us know immediately](https://modular.network "Modular-Network website") if you have discovered any issues or vulnerabilities with this library.

### Usage Example

```
pragma solidity ^0.4.21;

import "ethereum-libraries-wallet/contracts/WalletMainLib.sol";
import "ethereum-libraries-wallet/contracts/WalletAdminLib.sol";
import "ethereum-libraries-wallet/contracts/WalletGetterLib.sol";

contract YourWalletContract {
  using WalletMainLib for WalletMainLib.WalletData;

  WalletMainLib.WalletData public wallet;

  event Deposit(uint value);

  function YourWalletContract() {
    address[] memory _owners = new address[](5);//Define initial account owners with your owners
    _owners[0] = 0xb4e205cd196bbe4b1b3767a5e32e15f50eb79623;
    _owners[1] = 0x40333d950b4c682e8aad143c216af52877d828bf;
    _owners[2] = 0x0a1f4fcde83ba12ee8343488964811218da3e00e;
    _owners[3] = 0x79b63228ff63659248b7c688870de388bdcf0c14;
    _owners[4] = 0x36994c7cff11859ba8b9715120a68aa9499329ee;
    wallet.init(_owners,4,3,1,100000000000000000000);
  }

  //Payable fallback function
  function() payable {
    Deposit(msg.value);
  }

  /*Getters*/

  function owners() constant returns (address[51]) {//Returns fixed array until fork
    return wallet.getOwners();
  }

  function ownerIndex(address _owner) constant returns (uint) {
    return wallet.getOwnerIndex(_owner);
  }

  ...
}
```

## Functions

The following is the list of functions available to use in your smart contract.

### Primary Functions

#### init(WalletMainLib.WalletData storage, address[], uint256, uint256, uint256, uint256)   
*(WalletMainLib.sol, line 88)*

Constructor. Initializes the wallet in the calling contract's storage.  Caller passes in owners and signature settings for the wallet.  Owners must be valid ethereum addresses and signature requirements must be greater than zero and less than or equal to the number of owners. `_majorThreshold` parameter should set the daily spend limit for minor ether transactions in wei.

##### Arguments
**WalletMainLib.WalletData** self The storage wallet in the calling contract.   
**address[]** `_owners` Array of initial wallet owner addresses   
**uint256** `_requiredAdmin` The number of signatures required for administrative changes   
**uint256** `_requiredMajor` The number of signatures required for major transactions   
**uint256** `_requiredMinor` The number of signatures required for minor transactions   
**uint256** `_majorThreshold` The daily Ether spend threshold for transactions to become major, in units of wei

##### Returns
**bool**   

#### serveTx(WalletMainLib.WalletData, address, uint256, bytes, bool, bytes)   
*(WalletMainLib.sol, line 261)*

Sends the specified amount of Ether or tokens from the Wallet to an address.  This function requires a certain number of signatures from the wallet owners, indicated by requiredMinor for minor transactions and requiredMajor for major transactions.  If it is the first call with the given parameters, the transaction is created and a confirmation from the sender is recorded.  Additional calls sent from different owners but with the same parameters act as confirmations of the transaction.  If a previously confirmed owner calls this function with the same arguments for the pending transaction, but with the confirm flag set to false, their confirmation for the transaction will be revoked.  When the confirmations reach the required number, the transaction is executed.

##### Arguments
**WalletMainLib.WalletData** self The storage wallet in the calling contract.   
**address** `_to` Intended recipient of transaction.   
**uint256** `_value` Amount of Ether to be sent.   
**bytes** `_txData` Any transaction data to be sent to recipient.   
**bool** `_confirm` True if initiaing or confirming a transaction, false if revoking a signature.   
**bytes** `_data` Data for this call sent automatically by the calling contract.   

##### Returns
**bool** True if transaction confirmed or revoked successfully   
**bytes32** The transaction id which can be provided to `confirmTx` or `revokeConfirm`.   

#### confirmTx(WalletMainLib.WalletData storage, bytes32)   
*(WalletMainLib.sol, line 351)*

Confirms the specified pending transaction with the sender's signature.  If the transaction does not exist, the call will fail.  If the callers signature is the final signature needed for the transaction to succeed, the transaction will execute.

##### Arguments
**WalletMainLib.WalletData** self   
**bytes32** `_id`

##### Returns
**bool**   

#### revokeConfirm(WalletMainLib.WalletData storage, bytes32)   
*(WalletMainLib.sol, line 391)*

Revokes the sender's confirmation from a pending transaction.  If the transaction does not exist or has already succeeded, the call will fail.  The caller also needs to have already confirmed the transaction.

##### Arguments
**WalletMainLib.WalletData** self   
**bytes32** `_id`

##### Returns
**bool**   

### Administrative Functions

These functions are for performing actions that change the administrative settings of the Wallet contract such as owners, major/minor transaction threshholds, and number of signatures required. They behave almost exactly like ServeTx behaves above, but with requiredAdmin number of signatures required to execute changes.   

#### changeOwner(WalletMainLib.WalletData storage, address, address, bool, bytes)   
*(WalletAdminLib.sol, line 139)*

Changes owner address to a new address. bool should be true if confirming or initiating the transaction and false if revoking a confirmation. bytes parameter should be passed as msg.data from wallet contract.

##### Arguments
**WalletMainLib.WalletData** self   
**adress** `_from`   
**address** `_to`   
**bool** `_confirm`   
**bytes** `_data`

##### Returns
**bool**   
**bytes32**   

#### addOwner(WalletMainLib.WalletData storage, address, bool, bytes)   
*(WalletAdminLib.sol, line 209)*

Adds a new user as an owner of the wallet.

##### Arguments
**WalletMainLib.WalletData** self   
**adress** `_newOwner`   
**bool** `_confirm`   
**bytes** `_data`

##### Returns
**bool**   
**bytes32**   

#### removeOwner(WalletMainLib.WalletData storage, address, bool, bytes)   
*(WalletAdminLib.sol, line 280)*

Removes an existing owner from the wallet.

##### Arguments
**WalletMainLib.WalletData** self   
**adress** `_ownerRemoving`   
**bool** `_confirm`   
**bytes** `_data`

##### Returns
**bool**   
**bytes32**   

#### changeRequiredAdmin(WalletMainLib.WalletData storage, uint256, bool, bytes)   
*(WalletAdminLib.sol, line 351)*

Changes the number of signatures required to confirm administrative changes.

##### Arguments
**WalletMainLib.WalletData** self   
**uint256** `_requiredAdmin`   
**bool** `_confirm`   
**bytes** `_data`

##### Returns
**bool**   
**bytes32**   

#### changeRequiredMajor(WalletMainLib.WalletData storage, uint256, bool, bytes)   
*(WalletAdminLib.sol, line 418)*

Changes the number of signatures required to confirm major transactions.

##### Arguments
**WalletMainLib.WalletData** self   
**uint256** `_requiredMajor`   
**bool** `_confirm`   
**bytes** `_data`

##### Returns
**bool**   
**bytes32**   

#### changeRequiredMinor(WalletMainLib.WalletData storage, uint256, bool, bytes)   
*(WalletAdminLib.sol, line 485)*

Changes the number of signatures required to confirm minor transactions.

##### Arguments
**WalletMainLib.WalletData** self   
**uint256** `_requiredMinor`   
**bool** `_confirm`   
**bytes** `_data`

##### Returns
**bool**   
**bytes32**   

#### changeMajorThreshold(WalletMainLib.WalletData storage, address, address, bool, bytes)   
*(WalletAdminLib.sol, line 553)*

Changes the threshold of tokens or wei spent per day that needs to be crossed for the transaction to be considered major.

##### Arguments
**WalletMainLib.WalletData** self   
**adress** `_from`   
**address** `_to`   
**bool** `_confirm`   
**bytes** `_data`

##### Returns
**bool**   
**bytes32**   

### Getter Functions

#### getOwners(WalletMainLib.WalletData storage)   
*(WalletGetterLib.sol, line 40)*

Get list of wallet owners, will return fixed 50 item array until Metro fork.

##### Arguments
**WalletMainLib.WalletData** self   

##### Returns
**address[51]**   

#### getOwnerIndex(WalletMainLib.WalletData storage)   
*(WalletGetterLib.sol, line 52)*

Get index of an owner.

##### Arguments
**WalletMainLib.WalletData** self   

##### Returns
**uint256**   

#### getMaxOwners(WalletMainLib.WalletData storage)   
*(WalletGetterLib.sol, line 59)*

Get max number of wallet owners.

##### Arguments
**WalletMainLib.WalletData** self   

##### Returns
**uint256**   

#### getOwnerCount(WalletMainLib.WalletData storage)   
*(WalletGetterLib.sol, line 66)*

Get number of wallet owners.

##### Arguments
**WalletMainLib.WalletData** self   

##### Returns
**uint256**   

#### getRequiredAdmin(WalletMainLib.WalletData storage)   
*(WalletGetterLib.sol, line 73)*

Get sig requirements for administrative changes.

##### Arguments
**WalletMainLib.WalletData** self   

##### Returns
**uint256**   

#### getRequiredMinor(WalletMainLib.WalletData storage)   
*(WalletGetterLib.sol, line 80)*

Get sig requirements for minor tx spends.

##### Arguments
**WalletMainLib.WalletData** self   

##### Returns
**uint256**   

#### getRequiredMajor(WalletMainLib.WalletData storage)   
*(WalletGetterLib.sol, line 87)*

Get sig requirements for major tx spends.

##### Arguments
**WalletMainLib.WalletData** self   

##### Returns
**uint256**   

#### getCurrentSpend(WalletMainLib.WalletData storage, address)   
*(WalletGetterLib.sol, line 95)*

Get current day spend for token.

##### Arguments
**WalletMainLib.WalletData** self   
**address** `_token` Address of the token contract, use 0 for ether.   

##### Returns
**uint256[2]** 0-index is day timestamp, 1-index is the day spend   

#### getMajorThreshold(WalletMainLib.WalletData storage, address)   
*(WalletGetterLib.sol, line 106)*

Get major tx threshold per token.

##### Arguments
**WalletMainLib.WalletData** self   
**address** `_token`   

##### Returns
**uint256**   

#### getTransactionLength(WalletMainLib.WalletData storage, bytes32)   
*(WalletGetterLib.sol, line 114)*

Get the number of tx's with the same id.

##### Arguments
**WalletMainLib.WalletData** self   
**bytes32** `_id`   

##### Returns
**uint256** Number of transactions with this id, can be used to query for specific tx, see `getTransactionConfirms`   

#### getTransactionConfirms(WalletMainLib.WalletData storage, bytes32, uint256)   
*(WalletGetterLib.sol, line 123)*

Get list of confirmations for a tx, use `getTransactionLength` to get latest number.

##### Arguments
**WalletMainLib.WalletData** self   
**bytes32** `_id`   
**uint256** `_number`   

##### Returns
**uint256[50]** List of confirmations, fixed at 50 items until Metro fork   

#### getTransactionConfirmCount(WalletMainLib.WalletData storage, bytes32, uint256)   
*(WalletGetterLib.sol, line 140)*

Retrieve tx confirmation count.

##### Arguments
**WalletMainLib.WalletData** self   
**bytes32** `_id`   
**uint256** `_number`   

##### Returns
**uint256** The current number of tx confirmations.   

#### getTransactionSuccess(WalletMainLib.WalletData storage, bytes32, uint256)   
*(WalletGetterLib.sol, line 153)*

Retrieve if transaction was successful.

##### Arguments
**WalletMainLib.WalletData** self   
**bytes32** `_id`  
**uint256** `_number`   

##### Returns
**bool**   
