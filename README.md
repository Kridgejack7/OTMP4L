/**
* Flash Loan of 1000 DAI
*/
address receiver = address(this) // Can also be a separate contract
address asset = "0x6b175474e89094c44da98b954eedeac495271d0f"; // Dai
uint256 amount = 1000 * 1e18;

// If no params are needed, use an empty params:
bytes memory params = "";
// Else encode the params like below (bytes encoded param of type `address` and `uint`)
// bytes memory params = abi.encode(address(this), 1234);

ILendingPool lendingPool = ILendingPool(addressesProvider.getLendingPool());
lendingPool.flashLoan(address(this), asset, amount, params);
