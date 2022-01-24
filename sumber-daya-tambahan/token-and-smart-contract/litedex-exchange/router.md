# Router

## Info Contract

**Nama Contract:** LitedexRouter\
**Contract address:** 0xb05A6B43020F67784275b2ce3be6c34c7D564c04 **(Rinkeby)**

Lihat[ Litedex: Router Contract on Rinkeby.](https://rinkeby.etherscan.io/address/0xb05a6b43020f67784275b2ce3be6c34c7d564c04#code)

**LitedexRouter di BSC Mainnet sedang diaudit oleh CertiK, nantikan update terbaru.**

## Read functions

### WETH

```
function WETH() external pure returns (address);
```

Mengembalikan canonical address untuk[ token WETH](https://rinkeby.etherscan.io/address/0xc778417e063141139fce010982780140aa0cd5ab) (WETH menjadi sisa dari asal network Ethereum).

### factory

```
function factory() external pure returns (address);
```

Mengembalikan canonical address untuk [LitedexFactory](https://rinkeby.etherscan.io/address/0x154719241ed12011c0a722ca5226ee2099a82d38).

### getAmountOut

```
function getAmountOut(uint amountIn, uint reserveIn, uint reserveOut) internal pure returns (uint amountOut);
```

### getAmountIn

```
function getAmountIn(uint amountOut, uint reserveIn, uint reserveOut) internal pure returns (uint amountIn);
```

### getAmountsOut

```
function getAmountsOut(uint amountIn, address[] memory path) internal view returns (uint[] memory amounts);
```

### getAmountsIn

```
function getAmountsOut(uint amountIn, address[] memory path) internal view returns (uint[] memory amounts);
```

### quote

```
function quote(uint amountA, uint reserveA, uint reserveB) internal pure returns (uint amountB);
```

## Write functions

### addLiquidity

```
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

Menambahkan liquidity ke pool BEP20⇄BEP20.

| Nama           | Tipe      | Deskripsi                                                         |
| -------------- | --------- | ----------------------------------------------------------------- |
| tokenA         | `address` | Contract address satu token dari liquidity pair, Anda.            |
| tokenB         | `address` | Contract address token lain dari pasangan liquidity, Anda.        |
| amountADesired | `uint`    | Jumlah tokenA yang ingin Anda berikan sebagai liquidity.          |
| amountBDesired | `uint`    | Jumlah tokenB yang ingin Anda berikan sebagai liquidity.          |
| amountAMin     | `uint`    | Jumlah minimum tokenA yang disediakan (dampak slippage).          |
| amountBMin     | `uint`    | Jumlah minimum tokenB yang harus disediakan (dampak slippage).    |
| to             | `address` | Address penerima LP Token.                                        |
| deadline       | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi. |

### addLiquidityETH

```
function addLiquidityETH(
  address token,
  uint amountTokenDesired,
  uint amountTokenMin,
  uint amountETHMin,
  address to,
  uint deadline
) external payable returns (uint amountToken, uint amountETH, uint liquidity);
```

Menambahkan liquidity ke pool a BEP20⇄WBNB pool.

| Nama               | Tipe      | Deskripsi                                                         |
| ------------------ | --------- | ----------------------------------------------------------------- |
| addLiquidityETH    | `uint`    | Jumlah yang harus dibayar dalam BNB.                              |
| token              | `address` | Contract address untuk menambah liquidity.                        |
| amountTokenDesired | `uint`    | Jumlah token yang ingin Anda berikan sebagai liquidity.           |
| amountTokenMin     | `uint`    | Jumlah minimum token yang harus disediakan (dampak slippage).     |
| amountETHMin       | `uint`    | Jumlah minimum BNB yang harus disediakan (dampak slippage).       |
| to                 | `address` | Address penerima LP Token.                                        |
| deadline           | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi. |

### removeLiquidity

```
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

Menghapus liquidity dari pool BEP20⇄BEP20.

| Nama       | Tipe      | Deskripsi                                                         |
| ---------- | --------- | ----------------------------------------------------------------- |
| tokenA     | `address` | Contract address satu token dari pasangan liquidity Anda.         |
| tokenB     | `address` | Contract address token lain dari pasangan liquidity, Anda.        |
| liquidity  | `uint`    | Jumlah Token LP yang akan dihapus.                                |
| amountAMin | `uint`    | Jumlah minimum tokenA yang harus dihapus (dampak slippage).       |
| amountBMin | `uint`    | Jumlah minimum tokenB yang harus dihapus (dampak slippage).       |
| to         | `address` | Address penerima LP Token.                                        |
| deadline   | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi. |

### removeLiquidityETH

```
function removeLiquidityETH(
  address token,
  uint liquidity,
  uint amountTokenMin,
  uint amountETHMin,
  address to,
  uint deadline
) external returns (uint amountToken, uint amountETH);
```

Menghapus liquidity dari pool BEP20⇄WBNB.

| Nama           | Tipe      | Deskripsi                                                         |
| -------------- | --------- | ----------------------------------------------------------------- |
| token          | `address` | Contract address token untuk menghilangkan liquidity.             |
| liquidity      | `uint`    | Jumlah Token LP yang akan dihapus.                                |
| amountTokenMin | `uint`    | Jumlah minimum token yang harus dihapus (dampak slippage).        |
| amountETHMin   | `uint`    | Jumlah minimum BNB yang harus dihapus (dampak slippage).          |
| to             | `address` | Address penerima LP Token.                                        |
| deadline       | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi. |

### removeLiquidityETHSupportingFeeOnTransferTokens

```
function removeLiquidityETHSupportingFeeOnTransferTokens(
  address token,
  uint liquidity,
  uint amountTokenMin,
  uint amountETHMin,
  address to,
  uint deadline
) external returns (uint amountETH);
```

Menghapus liquidity dari BEP20⇄WBNB untuk token yang dikenakan biaya transfer.

| Nama           | Tipe      | Deskripsi                                                         |
| -------------- | --------- | ----------------------------------------------------------------- |
| token          | `address` | Contract address token untuk menghilangkan liquidity.             |
| liquidity      | `uint`    | Jumlah Token LP yang akan dihapus.                                |
| amountTokenMin | `uint`    | Jumlah minimum token yang harus dihapus (dampak slippage).        |
| amountETHMin   | `uint`    | Jumlah minimum token yang harus dihapus (dampak slippage).        |
| to             | `address` | Address penerima LP Token.                                        |
| deadline       | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi. |

### removeLiquidityETHWithPermit

```
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

Menghapus liquidity dari BEP20⇄WBNB dan menerima BNB, tanpa persetujuan sebelumnya, melalui izin.

| Nama           | Tipe      | Deskripsi                                                                                         |
| -------------- | --------- | ------------------------------------------------------------------------------------------------- |
| token          | `address` | Contract address token untuk menghilangkan liquidity.                                             |
| liquidity      | `uint`    | Jumlah Token LP yang akan dihapus.                                                                |
| amountTokenMin | `uint`    | Jumlah minimum token yang harus dihapus (dampak slippage).                                        |
| amountETHMin   | `uint`    | Jumlah minimum BNB yang harus dihapus (dampak slippage).                                          |
| to             | `address` | Address penerima LP Token.                                                                        |
| deadline       | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                 |
| approveMax     | `bool`    | Apakah, atau tidak jumlah persetujuan dalam tanda tangan adalah untuk likuiditas atau `uint(-1)`. |
| v              | `uint8`   | Komponen v dari tanda tangan izin.                                                                |
| r              | `bytes32` | Komponen r dari tanda tangan izin.                                                                |
| s              | `bytes32` | Komponen s dari tanda tangan izin.                                                                |

### removeLiquidityETHWithPermitSupportingFeeOnTransferTokens

```
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

Menghapus liquidity dari BEP20⇄WBNB dan menerima BNB melalui izin untuk token yang dikenakan biaya transfer.

| Nama           | Tipe      | Deskripsi                                                                                         |
| -------------- | --------- | ------------------------------------------------------------------------------------------------- |
| token          | `address` | Contract address token untuk menghilangkan liquidity.                                             |
| liquidity      | `uint`    | Jumlah Token LP yang akan dihapus.                                                                |
| amountTokenMin | `uint`    | Jumlah minimum token yang harus dihapus (dampak slippage).                                        |
| amountETHMin   | `uint`    | Jumlah minimum BNB yang harus dihapus (dampak slippage).                                          |
| to             | `address` | Address penerima LP token.                                                                        |
| deadline       | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                 |
| approveMax     | `bool`    | Apakah, atau tidak jumlah persetujuan dalam tanda tangan adalah untuk likuiditas atau `uint(-1)`. |
| v              | `uint8`   | Komponen v dari tanda tangan izin.                                                                |
| r              | `bytes32` | Komponen r dari tanda tangan izin.                                                                |
| s              | `bytes32` | Komponen s dari tanda tangan izin.                                                                |

### removeLiquidityWithPermit

```
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

Menghapus liquidity dari BEP20⇄BEP20, tanpa persetujuan sebelumnya, melalui izin.

| Nama           | Tipe      | Deskripsi                                                                                         |
| -------------- | --------- | ------------------------------------------------------------------------------------------------- |
| tokenA         | `address` | Contract address satu token dari pasangan liquidity Anda.                                         |
| tokenB         | `address` | Contract address token lain dari pair liquidity Anda.                                             |
| liquidity      | `uint`    | Jumlah Token LP yang akan dihapus.                                                                |
| amountTokenMin | `uint`    | Jumlah minimum token yang harus dihapus (dampak slippage).                                        |
| amountETHMin   | `uint`    | Jumlah minimum BNB yang harus dihapus (dampak slippage).                                          |
| to             | `address` | Address penerima LP Token.                                                                        |
| deadline       | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                 |
| approveMax     | `bool`    | Apakah, atau tidak jumlah persetujuan dalam tanda tangan adalah untuk likuiditas atau `uint(-1)`. |
| v              | `uint8`   | Komponen v dari tanda tangan izin.                                                                |
| r              | `bytes32` | Komponen r dari tanda tangan izin.                                                                |
| s              | `bytes32` | Komponen s dari tanda tangan izin.                                                                |

### swapETHForExactTokens

```
function swapETHForExactTokens(uint amountOut, address[] calldata path, address to, uint deadline)
  external
  payable
  returns (uint[] memory amounts);
```

Terima jumlah token output yang tepat untuk BNB sesedikit mungkin.

| Nama                  | Tipe      | Deskripsi                                                                                                                        |
| --------------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| swapETHForExactTokens | `uint`    | Jumlah BNB yang harus dibayar.                                                                                                   |
| amountOut             | `uint`    | Jumlah token yang akan diterima.                                                                                                 |
| path (address\[])     | `address` | Array token addresses. `path.length` harus >= 2. Pool untuk setiap pair address yang berurutan harus ada dan memiliki liquidity. |
| to                    | `address` | Address penerima.                                                                                                                |
| deadline              | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                                                |

### swapExactETHForTokens

```
function swapExactETHForTokens(uint amountOutMin, address[] calldata path, address to, uint deadline)
  external
  payable
  returns (uint[] memory amounts);
```

Terima token output sebanyak mungkin untuk jumlah BNB yang tepat.

| Nama                  | Tipe      | Deskripsi                                                                                                                        |
| --------------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| swapExactETHForTokens | `uint`    | Jumlah BNB yang harus dibayar.                                                                                                   |
| amountOutMin          | `uint`    | Jumlah minimum token yang akan diterima.                                                                                         |
| path (address\[])     | `address` | Array token addresses. `path.length` harus >= 2. Pool untuk setiap pair address yang berurutan harus ada dan memiliki liquidity. |
| to                    | `address` | Address penerima.                                                                                                                |
| deadline              | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                                                |

### swapExactETHForTokensSupportingFeeOnTransferTokens

```
function swapExactETHForTokensSupportingFeeOnTransferTokens(
  uint amountOutMin,
  address[] calldata path,
  address to,
  uint deadline
) external payable;
```

Terima token output sebanyak mungkin untuk jumlah BNB yang tepat. Mendukung token yang dikenakan biaya saat transfer.

| Nama                                               | Tipe      | Deskripsi                                                                                                                        |
| -------------------------------------------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| swapExactETHForTokensSupportingFeeOnTransferTokens | `uint`    | Jumlah BNB yang harus dibayar.                                                                                                   |
| amountOutMin                                       | `uint`    | Jumlah minimum token yang akan diterima.                                                                                         |
| path (address\[])                                  | `address` | Array token addresses. `path.length` harus >= 2. Pool untuk setiap pair address yang berurutan harus ada dan memiliki liquidity. |
| to                                                 | `address` | Address penerima.                                                                                                                |
| deadline                                           | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                                                |

### swapExactTokensForETH

```
function swapExactTokensForETH(uint amountIn, uint amountOutMin, address[] calldata path, address to, uint deadline)
  external
  returns (uint[] memory amounts);
```

Terima BNB sebanyak mungkin untuk jumlah token input yang tepat.

| Nama              | Tipe      | Deskripsi                                                                                                                        |
| ----------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| amountIn          | `uint`    | Jumlah token input yang harus dibayar.                                                                                           |
| amountOutMin      | `uint`    | Jumlah minimum token yang akan diterima.                                                                                         |
| path (address\[]) | `address` | Array token addresses. `path.length` harus >= 2. Pool untuk setiap pair address yang berurutan harus ada dan memiliki liquidity. |
| to                | `address` | Address penerima.                                                                                                                |
| deadline          | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                                                |

### swapExactTokensForETHSupportingFeeOnTransferTokens

```
function swapExactTokensForETHSupportingFeeOnTransferTokens(
  uint amountIn,
  uint amountOutMin,
  address[] calldata path,
  address to,
  uint deadline
) external;
```

Terima BNB sebanyak mungkin untuk jumlah token yang tepat. Mendukung token yang dikenakan biaya saat transfer.

| Nama              | Tipe      | Deskripsi                                                                                                                        |
| ----------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| amountIn          | `uint`    | Jumlah token input yang harus dibayar.                                                                                           |
| amountOutMin      | `uint`    | Jumlah minimum token yang akan diterima.                                                                                         |
| path (address\[]) | `address` | Array token addresses. `path.length` harus >= 2. Pool untuk setiap pair address yang berurutan harus ada dan memiliki liquidity. |
| to                | `address` | Address penerima.                                                                                                                |
| deadline          | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                                                |

### swapExactTokensForTokens

```
function swapExactTokensForTokens(
  uint amountIn,
  uint amountOutMin,
  address[] calldata path,
  address to,
  uint deadline
) external returns (uint[] memory amounts);
```

Terima token output sebanyak mungkin untuk jumlah token input yang tepat.

| Nama              | Tipe      | Deskripsi                                                                                                                        |
| ----------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| amountIn          | `uint`    | Jumlah token input yang harus dibayar.                                                                                           |
| amountOutMin      | `uint`    | Jumlah minimum token yang akan diterima.                                                                                         |
| path (address\[]) | `address` | Array token addresses. `path.length` harus >= 2. Pool untuk setiap pair address yang berurutan harus ada dan memiliki liquidity. |
| to                | `address` | Address penerima.                                                                                                                |
| deadline          | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                                                |

### swapExactTokensForTokensSupportingFeeOnTransferTokens

```
function swapExactTokensForTokensSupportingFeeOnTransferTokens(
  uint amountIn,
  uint amountOutMin,
  address[] calldata path,
  address to,
  uint deadline
) external;
```

Terima token output sebanyak mungkin untuk jumlah token input yang tepat. Mendukung token yang dikenakan biaya saat transfer.

| Nama              | Tipe      | Deskripsi                                                                                                                        |
| ----------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| amountIn          | `uint`    | Jumlah token input yang harus dibayar.                                                                                           |
| amountOutMin      | `uint`    | Jumlah minimum token yang akan diterima.                                                                                         |
| path (address\[]) | `address` | Array token addresses. `path.length` harus >= 2. Pool untuk setiap pair address yang berurutan harus ada dan memiliki liquidity. |
| to                | `address` | Address penerima.                                                                                                                |
| deadline          | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                                                |

### swapTokensForExactETH

```
function swapTokensForExactETH(uint amountOut, uint amountInMax, address[] calldata path, address to, uint deadline)
  external
  returns (uint[] memory amounts);
```

Terima jumlah ETH yang tepat untuk token input sesedikit mungkin.

| Nama              | Tipe      | Deskripsi                                                                                                                        |
| ----------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| amountOut         | `uint`    | Jumlah token input yang harus dibayar.                                                                                           |
| amountInMax       | `uint`    | Jumlah minimum token yang harus diinput.                                                                                         |
| path (address\[]) | `address` | Array token addresses. `path.length` harus >= 2. Pool untuk setiap pair address yang berurutan harus ada dan memiliki liquidity. |
| to                | `address` | Address penerima.                                                                                                                |
| deadline          | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                                                |

### swapTokensForExactTokens

```
function swapTokensForExactTokens(
  uint amountOut,
  uint amountInMax,
  address[] calldata path,
  address to,
  uint deadline
) external returns (uint[] memory amounts);
```

Receive an exact amount of output tokens for as few input tokens as possible.

| Nama              | Tipe      | Deskripsi                                                                                                                        |
| ----------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------- |
| amountOut         | `uint`    | Jumlah token input yang harus dibayar.                                                                                           |
| amountInMax       | `uint`    | Jumlah minimum token yang harus diinput.                                                                                         |
| path (address\[]) | `address` | Array token addresses. `path.length` harus >= 2. Pool untuk setiap pair address yang berurutan harus ada dan memiliki liquidity. |
| to                | `address` | Address penerima.                                                                                                                |
| deadline          | `uint`    | Batas waktu Unix timestamp, di mana transaksi harus dikonfirmasi.                                                                |

## Interface

```
pragma solidity >=0.6.2;

interface ILitedexRouter01 {
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

pragma solidity >=0.6.2;

interface ILitedexRouter02 is ILitedexRouter01 {
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
