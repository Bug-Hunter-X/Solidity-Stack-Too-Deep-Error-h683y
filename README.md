# Solidity Stack Too Deep Bug

This repository demonstrates a common Solidity bug: the 'Stack too deep' error.  This error occurs when a function's local variables consume more stack space than available.  The provided example shows the error and its solution using memory allocation.

## Bug Description
The `stackTooDeep` function attempts to perform calculations using a loop and local variables. When `_value` is large, the function's local variable usage exceeds the Ethereum Virtual Machine (EVM)'s stack limit. This results in the "Stack too deep" error.

## Solution
The solution involves storing variables in memory (`memory`) instead of the stack. This significantly increases the storage space available, avoiding the stack overflow issue. 

## How to reproduce
1. Clone this repository.
2. Compile and deploy the `stackTooDeepBug.sol` contract. 
3. Call the function with a sufficiently large argument (e.g., a value greater than 1024). This will trigger the "Stack too deep" error.
4. Compile and deploy `stackTooDeepSolution.sol`. This version avoids the error using memory.