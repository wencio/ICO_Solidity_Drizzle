### ICO Contract README

The ICO.sol contract facilitates an Initial Coin Offering (ICO) by allowing the sale of tokens to investors over a specified period. It includes functionalities for managing the ICO process, token sales, and administrative tasks.

#### Description

This contract contains functions to initialize and manage the ICO, as well as to administer funds and distribute tokens to investors at the end of the sale period.

#### Contract Structure

The contract is structured as follows:

- **State Variables**:
  - `sales`: Stores information about sales made during the ICO.
  - `investors`: Mapping that stores investors' addresses and their authorization status.
  - `token`: Address of the associated ERC20 token contract.
  - `admin`: Address of the contract administrator.
  - `end`: Timestamp indicating the end of the ICO.
  - `price`: Sale price of the tokens.
  - `availableTokens`: Quantity of tokens available for sale.
  - `minPurchase`: Minimum purchase amount allowed per investor.
  - `maxPurchase`: Maximum purchase amount allowed per investor.
  - `released`: State indicating if the tokens have been distributed to investors.

- **Main Functions**:
  - `start`: Initializes the ICO with specific parameters.
  - `whitelist`: Allows the administrator to authorize specific investors.
  - `buy`: Allows investors to buy tokens during the ICO.
  - `release`: Distributes tokens to investors at the end of the ICO.
  - `withdraw`: Allows the administrator to withdraw raised funds at the end of the ICO.

- **Modifiers**:
  - `icoActive`: Verifies if the ICO is active.
  - `icoNotActive`: Verifies if the ICO is not active.
  - `icoEnded`: Verifies if the ICO has ended.
  - `tokensNotReleased`: Verifies if the tokens have not been distributed.
  - `tokensReleased`: Verifies if the tokens have been distributed.
  - `onlyInvestors`: Verifies if the sender is an authorized investor.
  - `onlyAdmin`: Verifies if the sender is the contract administrator.

#### Drizzle Frontend

The frontend built with Drizzle provides a user interface to interact with the ICO contract. It consists of three main components:

- **ICOInfo**: Displays relevant information about the ICO, such as token price, sale duration, etc.
- **Investor**: Allows investors to purchase tokens during the ICO.
- **Admin**: Provides administrative functionalities, such as starting the ICO, authorizing investors, distributing tokens, etc.

The `drizzleOptions.js` file contains the Drizzle configuration used to connect the frontend with the smart contract.

### Usage Notes

- Before using the application, ensure to configure Drizzle correctly with the desired blockchain network and the corresponding smart contracts.
- Only the designated administrator has authority to initiate the ICO, authorize investors, distribute tokens, and withdraw funds.

This README provides an overview of the ICO contract and its associated frontend. For detailed instructions on how to use the application, refer to additional documentation or comments within the source code.
