title: Pillars new features
comments: false
---

# PoS Mining

## How to start PoS mining
Please follow the steps to start PoS mining:
1. Register a avatar.
2. Lock at least 1000 `ETP` by call `lock` with the avatar. The minimum lock height range is 100000.
3. The avatar should holds at least one `UTXO` which has at least 1000 `ETP` and over 1000 height maturity. 
4. `startmining` with option `-c pos`.

## Tips
It is easy to mine PoS block for avatar that has many `UTXO`s which has at least 1000 `ETP`.

# MST Mining

## How to start MST mining

### MST issuer
`MST` issuer should specify the `MST` mining subsidy parameters(`--subsidy`) when he issue a `MST` if he want the `MST` to be mined.

The format of `--subsidy` parameter is `initial:unit32,interval:unit32,base:float`. 

And `MST` mining reword is calculated by：`initial * pow(base, (block_height/interval))`.

#### Example
issue:
`./mvs-cli issue testacc testacc MST.MINING -s "initial:300000000,interval:500000,base:0.95"`

`MST` mining reword = 300000000 * pow(0.95, (Current block height - Height shen MST issued) / 500000).

### 矿工
Miner `startmining` with option `--symbol` and the symbol of `MST` to be mined.