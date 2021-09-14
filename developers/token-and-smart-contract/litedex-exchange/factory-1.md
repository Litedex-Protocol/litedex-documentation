# Factory

## Contract Information

**Contract name:** LitedexFactory  
**Contract address:** 0x154719241ed12011c0A722ca5226Ee2099a82D38 **\(Rinkeby\)**

View the [Litedex: Factory Contract on Rinkeby](https://rinkeby.etherscan.io/address/0x154719241ed12011c0a722ca5226ee2099a82d38#code).

## Read functions

### getPair

```text
function getPair(address tokenA, address tokenB) external view returns (address pair);
```

Address for `tokenA` and address for `tokenB` return address of pair contract \(where one exists\).

`tokenA` and `tokenB` order is interchangeable.

Returns `0x0000000000000000000000000000000000000000` as address where no pair exists.

### allPairs

```text
function allPairs(uint) external view returns (address pair);
```

Returns the address of the `n`th pair \(`0`-indexed\) created through the Factory contract.

Returns `0x0000000000000000000000000000000000000000` where pair has not yet been created.

Begins at `0` for first created pair.

### allPairsLength

```text
function allPairsLength() external view returns (uint);
```

Displays the current number of pairs created through the Factory contract as an integer.

### feeTo

```text
function feeTo() external view returns (address);
```

The address to where non-LP-holder fees are sent.

### feeToSetter

```text
function feeToSetter() external view returns (address);
```

The address with permission to set the feeTo address.

## Write functions

### createPair

```text
function createPair(address tokenA, address tokenB) external returns (address pair);
```

Creates a pair for `tokenA` and `tokenB` where a pair doesn't already exist.

`tokenA` and `tokenB` order is interchangeable.

Emits `PairCreated` \(see Events\).

### setFeeTo

```text
function setFeeTo(address) external;
```

Sets address for `feeTo`.

### setFeeToSetter

```text
function setFeeToSetter(address) external;
```

Sets address for permission to adjust `feeTo`.

## Events

### PairCreated

```text
event PairCreated(address indexed token0, address indexed token1, address pair, uint);
```

Emitted whenever a `createPair` creates a new pair.

`token0` will appear before `token1` in sort order.

The final `uint` log value will be `1` for the first pair created, `2` for the second, etc.

## Interface

```text
pragma solidity =0.5.16;


interface ILitedexFactory {
    event PairCreated(address indexed token0, address indexed token1, address pair, uint);

    function feeTo() external view returns (address);
    function feeToSetter() external view returns (address);

    function getPair(address tokenA, address tokenB) external view returns (address pair);
    function allPairs(uint) external view returns (address pair);
    function allPairsLength() external view returns (uint);

    function createPair(address tokenA, address tokenB) external returns (address pair);

    function setFeeTo(address) external;
    function setFeeToSetter(address) external;
}
```

