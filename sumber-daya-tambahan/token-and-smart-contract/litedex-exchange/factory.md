# Factory

## Informasi Contract

**Nama Contract**: LitedexFactory&#x20;

**Contract Address**: 0x154719241ed12011c0A722ca5226Ee2099a82D38 **(Rinkeby)**

Lihat [Litedex: Factory Contract on Rinkeby](https://rinkeby.etherscan.io/address/0x154719241ed12011c0a722ca5226ee2099a82d38#code).

**LitedexFactory di BSC Mainnet sedang diaudit oleh CertiK, nantikan update terbaru.**

## Read functions

### getPair

```
function getPair(address tokenA, address tokenB) external view returns (address pair);
```

Address untuk `tokenA` dan address untuk `tokenB` mengembalikan address pair contract (jika ada).

urutan `tokenA` dan `tokenB` dapat dipertukarkan.

Mengembalikan `0x0000000000000000000000000000000000000000` sebagai address dimana tidak ada pair.

### allPairs

```
function allPairs(uint) external view returns (address pair);
```

Mengembalikan address dari `n`th pair (`0`-indexed) yang dibuat melalui Factory contract.

Mengembalikan `0x0000000000000000000000000000000000000000` dimana pair belum dibuat.

Dimulai dari `0` untuk pasangan pertama yang dibuat.

### allPairsLength

```
function allPairsLength() external view returns (uint);
```

Menampilkan jumlah pair saat ini yang dibuat melalui Factory contract sebagai integer.

### feeTo

```
function feeTo() external view returns (address);
```

Address tujuan pengiriman biaya non-LP-holder.

### feeToSetter

```
function feeToSetter() external view returns (address);
```

Address dengan izin untuk mengatur  feeTo address.

## Write functions

### createPair

```
function createPair(address tokenA, address tokenB) external returns (address pair);
```

Membuat pair untuk `tokenA` dan `tokenB` dimana pair belum ada.

urutan `tokenA` dan `tokenB` dapat dipertukarkan.

Emits `PairCreated` (melihat Events).

### setFeeTo

```
function setFeeTo(address) external;
```

Menetapkan address untuk `feeTo`.

### setFeeToSetter

```
function setFeeToSetter(address) external;
```

Menetapkan address untuk izin menyesuaikan `feeTo`.

## Events

### PairCreated

```
event PairCreated(address indexed token0, address indexed token1, address pair, uint);
```

Dipancarkan setiap kali `createPair` membuat pair baru.

`token0` akan muncul sebelum `token1` dalam urutan pengurutan.

Nilai log `uint` terakhir adalah `1` untuk pasangan pertama yang dibuat, `2` untuk pasangan kedua, dst.

## Interface

```
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

