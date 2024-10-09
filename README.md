# Project Title

This simple smart contract is written in Solidity. The contract manages a token system with the ability to mint and burn tokens.

## Description

This Solidity contract, MyToken, manages a token system with minting and burning functionality. It allows new tokens to be created and assigned to users with the mint function, while the burn function reduces a user's token balance if they have enough. The contract also tracks the total supply of tokens and individual balances using public variables and a mapping.

## Getting Started

### Executing program

* How to run the program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```
contract MyToken {

    // public variables here
    string public tokenName = "ELLA";
    string public tokenAbbrev = "EBGW";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _val) public{
        totalSupply += _val;
        balances[_address] += _val;
    }

    // burn function
    function burn (address _address, uint _val) public{
        if (balances[_address] >= _val){
        totalSupply -= _val;
        balances[_address] -= _val;
        }
    }

}
```
* Step-by-step bullets
Deploy the contract:
- Go to Remix IDE (https://remix.ethereum.org).
- Paste the Solidity code into a new file.
- Navigate to the Deploy & Run Transactions panel.
- Select an account from the Account dropdown (choose the first one), then copy the address to your clipboard by clicking the copy button.

Mint tokens:
- In the Deployed Contracts section, expand the mint function by clicking the arrow beside it.
- In the _address field, paste the copied address (the one from step 1).
- In the _val field, input a value (for example, 1000), then click Transact to mint the tokens.
- Check the totalSupply by clicking the corresponding button—it should now reflect the newly minted tokens (e.g., 1000).
- Paste the same address into the balances function and click to check the balance—it should show the same value you minted (e.g., 1000).

Burn tokens:
- In the burn function, paste the same address into the _address field and enter a value to burn (e.g., 500), then click Transact.
- Check the totalSupply again—it should now show a reduced value (e.g., 500).
- Also, check the balance for the same address—it should now reflect the reduced amount (e.g., 500).

Attempt to burn more tokens than available:
- Try burning more tokens than the current balance (e.g., enter 1000 in the _val field and click Transact).
- The value will not change, as the balance is insufficient to burn the requested amount.

## Authors

Contributors names and contact info

Ella Belle G. Wong 
ex. [@ellabxlle](https://instagram.com/ellabxlle)


## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details
