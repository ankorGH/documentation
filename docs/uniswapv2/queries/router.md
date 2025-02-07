---
id: router
title: Router
---

## Imported types

### [Token](/uniswapv2/common-types#token)

```graphql
type Token {
  chainId: ChainId!
  address: String!
  currency: Currency!
}
```

### [TradeOptions](/uniswapv2/common-types#tradeoptions)

```graphql
type TradeOptions {
  allowedSlippage: String!
  recipient: String!
  unixTimestamp: UInt64!
  ttl: UInt32
  deadline: UInt32
  feeOnTransfer: Boolean
}
```

### [SwapParameters](/uniswapv2/common-types#swapparameters)

```graphql
type SwapParameters {
  methodName: String!
  args: [String!]!
  value: String!
}
```

### [TxOverrides](/uniswapv2/common-types#txoverrides)

```graphql
type TxOverrides {
  gasPrice: BigInt
  gasLimit: BigInt
}
```

### [ChainId](/uniswapv2/common-types#chainid)

```graphql
enum ChainId {
  MAINNET
  ROPSTEN
  RINKEBY
  GOERLI
  KOVAN
}
```

## Query schemas

### swapCallParameters

_Returns the parameters for the swap._

```graphql
  swapCallParameters(
    trade: Trade!,
    tradeOptions: TradeOptions!
  ): SwapParameters!
```

### estimateGas

_Estimates the gas being used in the swap._

```graphql
  estimateGas(
    parameters: SwapParameters!
    chainId: ChainId
  ): String!
```

### execCallStatic

_Returns empty string if call would be successful, otherwise returns solidity contract error._

```graphql
  execCallStatic(
    parameters: SwapParameters!
    chainId: ChainId!
    txOverrides: TxOverrides
  ): String!
```
