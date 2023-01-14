# Cosmos Zone APR Calculation


## APR 구하는 공식

```
Annual Provision = GET {Cosmos SDK REST Endpoint}/cosmos/mint/v1beta1/annual_provisions
Bonded Tokens = GET {Cosmos SDK Rest Endpoint}/cosmos/staking/v1beta1/pool

block_provision = Annual Provision / blocks_per_year-Param
Real Annual Provision = block_provision * blocks_per_Year-Real

Nominal APR = [Annual Provision * (1-Community Tax)] / Bonded Tokens ;
Real Staking APR = (Nominal APR) * [(Real Annual Provision) / (Annual Provision)]

Final Staking APR = (Real Staking APR) * (1-Validator’s commission)
```

## Run

```bash
npm i

COSMOS_REST_URL=https://cosmos-testnet.stayking.xyz:1317 npm start
```