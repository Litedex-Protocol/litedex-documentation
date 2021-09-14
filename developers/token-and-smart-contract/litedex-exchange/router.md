# Router

## Contract info

**Contract name:** LitedexRouter  
**Contract address:** 0xb05A6B43020F67784275b2ce3be6c34c7D564c04 **\(Rinkeby\)**

View the[ Litedex: Router Contract on Rinkeby.](https://rinkeby.etherscan.io/address/0xb05a6b43020f67784275b2ce3be6c34c7d564c04#code)

## Read functions

### WETH

```text
function WETH() external pure returns (address);
```

Returns the canonical address for [WETH token](https://rinkeby.etherscan.io/address/0xc778417e063141139fce010982780140aa0cd5ab) \(WETH being a vestige from Ethereum network origins\).

### factory

```text
function factory() external pure returns (address);
```

Returns the canonical address for [LitedexFactory](https://rinkeby.etherscan.io/address/0x154719241ed12011c0a722ca5226ee2099a82d38).

### getAmountOut

```text
function getAmountOut(uint amountIn, uint reserveIn, uint reserveOut) internal pure returns (uint amountOut);
```

### getAmountIn

```text
function getAmountIn(uint amountOut, uint reserveIn, uint reserveOut) internal pure returns (uint amountIn);
```

### getAmountsOut

```text
function getAmountsOut(uint amountIn, address[] memory path) internal view returns (uint[] memory amounts);
```

### getAmountsIn

```text
function getAmountsOut(uint amountIn, address[] memory path) internal view returns (uint[] memory amounts);
```

### quote

```text
function quote(uint amountA, uint reserveA, uint reserveB) internal pure returns (uint amountB);
```

## Write functions

### addLiquidity

```text
function addLiquidity(
  address tokenA,
  address tokenB,
  uint amountADesired,
  uint amountBDesired,
  uint amountAMin,
  uint amountBMin,
  address to,
  uint deadline
) external returns (uint amountA, uint amountB, uint liquidity);
```

Adds liquidity to a BEP20⇄BEP20 pool.

| Name | Type | Description |
| :--- | :--- | :--- |
| tokenA | `address` | The contract address of one token from your liquidity pair. |
| tokenB | `address` | The contract address of the other token from your liquidity pair. |
| amountADesired | `uint` | The amount of tokenA you'd like to provide as liquidity. |
| amountBDesired | `uint` | The amount of tokenA you'd like to provide as liquidity. |
| amountAMin | `uint` | The minimum amount of tokenA to provide \(slippage impact\). |
| amountBMin | `uint` | The minimum amount of tokenB to provide \(slippage impact\). |
| to | `address` | Address of LP Token recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### addLiquidityETH

```text
function addLiquidityETH(
  address token,
  uint amountTokenDesired,
  uint amountTokenMin,
  uint amountETHMin,
  address to,
  uint deadline
) external payable returns (uint amountToken, uint amountETH, uint liquidity);
```

Adds liquidity to a BEP20⇄WBNB pool.

| Name | Type |  |
| :--- | :--- | :--- |
| addLiquidityETH | `uint` | The payable amount in BNB. |
| token | `address` | The contract address of the token to add liquidity. |
| amountTokenDesired | `uint` | The amount of the token you'd like to provide as liquidity. |
| amountTokenMin | `uint` | The minimum amount of the token to provide \(slippage impact\). |
| amountETHMin | `uint` | The minimum amount of BNB to provide \(slippage impact\). |
| to | `address` | Address of LP Token recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### removeLiquidity

```text
function removeLiquidity(
  address tokenA,
  address tokenB,
  uint liquidity,
  uint amountAMin,
  uint amountBMin,
  address to,
  uint deadline
) external returns (uint amountA, uint amountB);
```

Removes liquidity from a BEP20⇄BEP20 pool.

| Name | Type |  |
| :--- | :--- | :--- |
| tokenA | `address` | The contract address of one token from your liquidity pair. |
| tokenB | `address` | The contract address of the other token from your liquidity pair. |
| liquidity | `uint` | The amount of LP Tokens to remove. |
| amountAMin | `uint` | The minimum amount of tokenA to remove \(slippage impact\). |
| amountBMin | `uint` | The minimum amount of tokenB to remove \(slippage impact\). |
| to | `address` | Address of LP Token recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### removeLiquidityETH

```text
function removeLiquidityETH(
  address token,
  uint liquidity,
  uint amountTokenMin,
  uint amountETHMin,
  address to,
  uint deadline
) external returns (uint amountToken, uint amountETH);
```

Removes liquidity from a BEP20⇄WBNB pool.

| Name | Type |  |
| :--- | :--- | :--- |
| token | `address` | The contract address of the token to remove liquidity. |
| liquidity | `uint` | The amount of LP Tokens to remove. |
| amountTokenMin | `uint` | The minimum amount of the token to remove \(slippage impact\). |
| amountETHMin | `uint` | The minimum amount of BNB to remove \(slippage impact\). |
| to | `address` | Address of LP Token recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### removeLiquidityETHSupportingFeeOnTransferTokens

```text
function removeLiquidityETHSupportingFeeOnTransferTokens(
  address token,
  uint liquidity,
  uint amountTokenMin,
  uint amountETHMin,
  address to,
  uint deadline
) external returns (uint amountETH);
```

Removes liquidity from a BEP20⇄WBNB for tokens that take a fee on transfer.

| Name | Type |  |
| :--- | :--- | :--- |
| token | `address` | The contract address of the token to remove liquidity. |
| liquidity | `uint` | The amount of LP Tokens to remove. |
| amountTokenMin | `uint` | The minimum amount of the token to remove \(slippage impact\). |
| amountETHMin | `uint` | The minimum amount of BNB to remove \(slippage impact\). |
| to | `address` | Address of LP Token recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### removeLiquidityETHWithPermit

```text
function removeLiquidityETHWithPermit(
  address token,
  uint liquidity,
  uint amountTokenMin,
  uint amountETHMin,
  address to,
  uint deadline,
  bool approveMax, uint8 v, bytes32 r, bytes32 s
) external returns (uint amountToken, uint amountETH);
```

Removes liquidity from a BEP20⇄WBNB and receives BNB, without pre-approval, via permit.

| Name | Type |  |
| :--- | :--- | :--- |
| token | `address` | The contract address of the token to remove liquidity. |
| liquidity | `uint` | The amount of LP Tokens to remove. |
| amountTokenMin | `uint` | The minimum amount of the token to remove \(slippage impact\). |
| amountETHMin | `uint` | The minimum amount of BNB to remove \(slippage impact\). |
| to | `address` | Address of LP Token recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |
| approveMax | `bool` | Whether or not the approval amount in the signature is for liquidity or `uint(-1)`. |
| v | `uint8` | The v component of the permit signature. |
| r | `bytes32` | The r component of the permit signature. |
| s | `bytes32` | The s component of the permit signature. |

### removeLiquidityETHWithPermitSupportingFeeOnTransferTokens

```text
function removeLiquidityETHWithPermitSupportingFeeOnTransferTokens(
  address token,
  uint liquidity,
  uint amountTokenMin,
  uint amountETHMin,
  address to,
  uint deadline,
  bool approveMax, uint8 v, bytes32 r, bytes32 s
) external returns (uint amountETH);
```

Removes liquidity from a BEP20⇄WBNB and receives BNB via permit for tokens that take a fee on transfer.

| Name | Type |  |
| :--- | :--- | :--- |
| token | `address` | The contract address of the token to remove liquidity. |
| liquidity | `uint` | The amount of LP Tokens to remove. |
| amountTokenMin | `uint` | The minimum amount of the token to remove \(slippage impact\). |
| amountETHMin | `uint` | The minimum amount of BNB to remove \(slippage impact\). |
| to | `address` | Address of LP Token recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |
| approveMax | `bool` | Whether or not the approval amount in the signature is for liquidity or `uint(-1)`. |
| v | `uint8` | The v component of the permit signature. |
| r | `bytes32` | The r component of the permit signature. |
| s | `bytes32` | The s component of the permit signature. |

### removeLiquidityWithPermit

```text
function removeLiquidityWithPermit(
  address tokenA,
  address tokenB,
  uint liquidity,
  uint amountAMin,
  uint amountBMin,
  address to,
  uint deadline,
  bool approveMax, uint8 v, bytes32 r, bytes32 s
) external returns (uint amountA, uint amountB);
```

Removes liquidity from a BEP20⇄BEP20, without pre-approval, via permit.

| Name | Type |  |
| :--- | :--- | :--- |
| tokenA | `address` | The contract address of one token from your liquidity pair. |
| tokenB | `address` | The contract address of the other token from your liquidity pair. |
| liquidity | `uint` | The amount of LP Tokens to remove. |
| amountTokenMin | `uint` | The minimum amount of the token to remove \(slippage impact\). |
| amountETHMin | `uint` | The minimum amount of BNB to remove \(slippage impact\). |
| to | `address` | Address of LP Token recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |
| approveMax | `bool` | Whether or not the approval amount in the signature is for liquidity or `uint(-1)`. |
| v | `uint8` | The v component of the permit signature. |
| r | `bytes32` | The r component of the permit signature. |
| s | `bytes32` | The s component of the permit signature. |

### swapETHForExactTokens

```text
function swapETHForExactTokens(uint amountOut, address[] calldata path, address to, uint deadline)
  external
  payable
  returns (uint[] memory amounts);
```

Receive an exact amount of output tokens for as little BNB as possible.

| Name | Type |  |
| :--- | :--- | :--- |
| swapETHForExactTokens | `uint` | Payable BNB amount. |
| amountOut | `uint` | The amount tokens to receive. |
| path \(address\[\]\) | `address` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Address of recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### swapExactETHForTokens

```text
function swapExactETHForTokens(uint amountOutMin, address[] calldata path, address to, uint deadline)
  external
  payable
  returns (uint[] memory amounts);
```

Receive an as many output tokens as possible for an exact amount of BNB.

| Name | Type |  |
| :--- | :--- | :--- |
| swapExactETHForTokens | `uint` | Payable BNB amount. |
| amountOutMin | `uint` | The minimum amount tokens to receive. |
| path \(address\[\]\) | `address` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Address of recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### swapExactETHForTokensSupportingFeeOnTransferTokens

```text
function swapExactETHForTokensSupportingFeeOnTransferTokens(
  uint amountOutMin,
  address[] calldata path,
  address to,
  uint deadline
) external payable;
```

Receive an as many output tokens as possible for an exact amount of BNB. Supports tokens that take a fee on transfer.

| Name | Type |  |
| :--- | :--- | :--- |
| swapExactETHForTokensSupportingFeeOnTransferTokens | `uint` | Payable BNB amount. |
| amountOutMin | `uint` | The minimum amount tokens to receive. |
| path \(address\[\]\) | `address` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Address of recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### swapExactTokensForETH

```text
function swapExactTokensForETH(uint amountIn, uint amountOutMin, address[] calldata path, address to, uint deadline)
  external
  returns (uint[] memory amounts);
```

Receive an as much BNB as possible for an exact amount of input tokens.

| Name | Type |  |
| :--- | :--- | :--- |
| amountIn | `uint` | Payable amount of input tokens. |
| amountOutMin | `uint` | The minimum amount tokens to receive. |
| path \(address\[\]\) | `address` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Address of recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### swapExactTokensForETHSupportingFeeOnTransferTokens

```text
function swapExactTokensForETHSupportingFeeOnTransferTokens(
  uint amountIn,
  uint amountOutMin,
  address[] calldata path,
  address to,
  uint deadline
) external;
```

Receive an as much BNB as possible for an exact amount of tokens. Supports tokens that take a fee on transfer.

| Name | Type |  |
| :--- | :--- | :--- |
| amountIn | `uint` | Payable amount of input tokens. |
| amountOutMin | `uint` | The minimum amount tokens to receive. |
| path \(address\[\]\) | `address` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Address of recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### swapExactTokensForTokens

```text
function swapExactTokensForTokens(
  uint amountIn,
  uint amountOutMin,
  address[] calldata path,
  address to,
  uint deadline
) external returns (uint[] memory amounts);
```

Receive an as many output tokens as possible for an exact amount of input tokens.

| Name | Type |  |
| :--- | :--- | :--- |
| amountIn | `uint` | Payable amount of input tokens. |
| amountOutMin | `uint` | The minimum amount tokens to receive. |
| path \(address\[\]\) | `address` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Address of recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### swapExactTokensForTokensSupportingFeeOnTransferTokens

```text
function swapExactTokensForTokensSupportingFeeOnTransferTokens(
  uint amountIn,
  uint amountOutMin,
  address[] calldata path,
  address to,
  uint deadline
) external;
```

Receive an as many output tokens as possible for an exact amount of input tokens. Supports tokens that take a fee on transfer.

| Name | Type |  |
| :--- | :--- | :--- |
| amountIn | `uint` | Payable amount of input tokens. |
| amountOutMin | `uint` | The minimum amount tokens to receive. |
| path \(address\[\]\) | `address` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Address of recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### swapTokensForExactETH

```text
function swapTokensForExactETH(uint amountOut, uint amountInMax, address[] calldata path, address to, uint deadline)
  external
  returns (uint[] memory amounts);
```

Receive an exact amount of ETH for as few input tokens as possible.

| Name | Type |  |
| :--- | :--- | :--- |
| amountOut | `uint` | Payable amount of input tokens. |
| amountInMax | `uint` | The minimum amount tokens to input. |
| path \(address\[\]\) | `address` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Address of recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

### swapTokensForExactTokens

```text
function swapTokensForExactTokens(
  uint amountOut,
  uint amountInMax,
  address[] calldata path,
  address to,
  uint deadline
) external returns (uint[] memory amounts);
```

Receive an exact amount of output tokens for as few input tokens as possible.

| Name | Type |  |
| :--- | :--- | :--- |
| amountOut | `uint` | Payable amount of input tokens. |
| amountInMax | `uint` | The minimum amount tokens to input. |
| path \(address\[\]\) | `address` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Address of recipient. |
| deadline | `uint` | Unix timestamp deadline by which the transaction must confirm. |

## Interface

```text
import '@uniswap/v2-core/contracts/interfaces/IPancakeRouter.sol';
```

```text
pragma solidity >=0.6.2;

interface IPancakeRouter01 {
    function factory() external pure returns (address);
    function WETH() external pure returns (address);

    function addLiquidity(
        address tokenA,
        address tokenB,
        uint amountADesired,
        uint amountBDesired,
        uint amountAMin,
        uint amountBMin,
        address to,
        uint deadline
    ) external returns (uint amountA, uint amountB, uint liquidity);
    function addLiquidityETH(
        address token,
        uint amountTokenDesired,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline
    ) external payable returns (uint amountToken, uint amountETH, uint liquidity);
    function removeLiquidity(
        address tokenA,
        address tokenB,
        uint liquidity,
        uint amountAMin,
        uint amountBMin,
        address to,
        uint deadline
    ) external returns (uint amountA, uint amountB);
    function removeLiquidityETH(
        address token,
        uint liquidity,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline
    ) external returns (uint amountToken, uint amountETH);
    function removeLiquidityWithPermit(
        address tokenA,
        address tokenB,
        uint liquidity,
        uint amountAMin,
        uint amountBMin,
        address to,
        uint deadline,
        bool approveMax, uint8 v, bytes32 r, bytes32 s
    ) external returns (uint amountA, uint amountB);
    function removeLiquidityETHWithPermit(
        address token,
        uint liquidity,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline,
        bool approveMax, uint8 v, bytes32 r, bytes32 s
    ) external returns (uint amountToken, uint amountETH);
    function swapExactTokensForTokens(
        uint amountIn,
        uint amountOutMin,
        address[] calldata path,
        address to,
        uint deadline
    ) external returns (uint[] memory amounts);
    function swapTokensForExactTokens(
        uint amountOut,
        uint amountInMax,
        address[] calldata path,
        address to,
        uint deadline
    ) external returns (uint[] memory amounts);
    function swapExactETHForTokens(uint amountOutMin, address[] calldata path, address to, uint deadline)
        external
        payable
        returns (uint[] memory amounts);
    function swapTokensForExactETH(uint amountOut, uint amountInMax, address[] calldata path, address to, uint deadline)
        external
        returns (uint[] memory amounts);
    function swapExactTokensForETH(uint amountIn, uint amountOutMin, address[] calldata path, address to, uint deadline)
        external
        returns (uint[] memory amounts);
    function swapETHForExactTokens(uint amountOut, address[] calldata path, address to, uint deadline)
        external
        payable
        returns (uint[] memory amounts);

    function quote(uint amountA, uint reserveA, uint reserveB) external pure returns (uint amountB);
    function getAmountOut(uint amountIn, uint reserveIn, uint reserveOut) external pure returns (uint amountOut);
    function getAmountIn(uint amountOut, uint reserveIn, uint reserveOut) external pure returns (uint amountIn);
    function getAmountsOut(uint amountIn, address[] calldata path) external view returns (uint[] memory amounts);
    function getAmountsIn(uint amountOut, address[] calldata path) external view returns (uint[] memory amounts);
}

// File: contracts\interfaces\IPancakeRouter02.sol

pragma solidity >=0.6.2;

interface IPancakeRouter02 is IPancakeRouter01 {
    function removeLiquidityETHSupportingFeeOnTransferTokens(
        address token,
        uint liquidity,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline
    ) external returns (uint amountETH);
    function removeLiquidityETHWithPermitSupportingFeeOnTransferTokens(
        address token,
        uint liquidity,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline,
        bool approveMax, uint8 v, bytes32 r, bytes32 s
    ) external returns (uint amountETH);

    function swapExactTokensForTokensSupportingFeeOnTransferTokens(
        uint amountIn,
        uint amountOutMin,
        address[] calldata path,
        address to,
        uint deadline
    ) external;
    function swapExactETHForTokensSupportingFeeOnTransferTokens(
        uint amountOutMin,
        address[] calldata path,
        address to,
        uint deadline
    ) external payable;
    function swapExactTokensForETHSupportingFeeOnTransferTokens(
        uint amountIn,
        uint amountOutMin,
        address[] calldata path,
        address to,
        uint deadline
    ) external;
}
```
