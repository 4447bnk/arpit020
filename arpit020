pragma solidity 0.8.18;

contract MyToken {

    string public name = "MyToken";          
    string public symbol = "MTK";            
    uint256 public totalSupply = 0;         

    mapping(address => uint256) public balances;
    event Mint(address indexed to, uint256 amount);

    
    event Burn(address indexed from, uint256 amount);

    function mint(address to, uint256 amount) public {
        
        totalSupply += amount;
        
        balances[to] += amount;
        
        emit Mint(to, amount);
    }
    function burn(address from, uint256 amount) public {
        Check if the balance of the specified address is greater than or equal to the amount to be burned
        require(balances[from] >= amount, "Insufficient balance to burn");

        Decrease the total supply by the amount of tokens burned
        totalSupply -= amount;
        Decrease the balance of the specified address by the amount of tokens burned
        balances[from] -= amount;
        Emit the Burn event
        emit Burn(from, amount);
    }
}
