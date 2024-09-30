Flashloan simulation with DEX arbitrage.  
MockFlashLoanProvider simulates Equalizer Finance wti zero fee.  
XToken is a generic ERC20 token having different values on different dexes.  
Dex 1 & 2 are two different dexes (addresses) that holds a XToken of various values.  
Argitrage will make the actual swap.  

After contract initializations the contracts will be supplied with XTokens.  
The dexes will be assigned various XToken values per dex.  
If dex1TokenPrice == dex2TokenPrice no arbitrage opportunity exists.  
DexTokenPrices are compared to determine arbigtrage direction.  
SwapAmount is determined to be the lowest balanceOf value of the Tokens per dex.  
    
XToken -> MockFlashLoanProvider  
Arbitrage flashloan <- MockFlashLoanProvider  
Arbitrage buys from one Dex and sells to the other Dex. (Buy low and sell high) //<-- probable error here, Arbitrage does not own XTokens borrowed??  
Once this step has been accomplished Arbitrage will repay the flashloah to MockFlashLoanProvider.    


To run this simulation and see errors in RED.  
In terminal 1: $ anvil  
In terminal 2: $ ./run.sh   
Make sure run.sh is executable or copy lines and run manually in terminal 2.  

Dependencies:  
https://book.getfoundry.sh/getting-started/installation    
forge install OpenZeppelin/openzeppelin-contracts

