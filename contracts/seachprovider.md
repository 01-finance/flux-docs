# SeachProvider

### unclaimedFlux

Search  how many FLUX token user can  claim.

```solidity
function unclaimedFlux(address user) public view returns (uint256)
```

### unclaimedFluxAtLoan

Search  how many FLUX token user can  claim from loan pool.

```solidity
/**
      @notice 获取借贷市场中尚未领取的Flux
      @return total 所有借贷市场累积未领取
      @return markets 借贷市场清单
      @return bySupply 每个借贷市场中对应的因存款而获得的未领取的FLUX代币
      @return byBorrow 每个借贷市场中对应的因借款而获得的未领取的FLUX代币
     */
    function unclaimedFluxAtLoan(address user)
        public
        view
        returns (
            uint256 total,
            address[] memory markets,
            uint256[] memory bySupply,
            uint256[] memory byBorrow
        );
```

Example

```javascript
var search = new etherjs.Contract(SeachProviderAddress, SeachProviderABI)
var result = await search.unclaimedFluxAtLoan(userAddress);

for(var i=0;i<result.markets.length;i++){
   console.log(`unclaimed ${  result.bySupply[i]/1e18 + result.byBorrow[i]/1e18 +  } FLUX on pool ${result.markets[i]}`);   
}

```



### unclaimedFluxAtStake

Search  how many FLUX token user can  claim from stake pool.

```solidity
function unclaimedFluxAtStake(address user)
        public
        view
        returns (
            uint256 total,
            address[] memory stakePools,
            uint256[] memory rewards
        );
```

Example

```javascript
var search = new etherjs.Contract(SeachProviderAddress, SeachProviderABI)
var result = await search.unclaimedFluxAtStake(userAddress);

for(var i=0;i<result.stakePools.length;i++){
   console.log(`unclaimed ${  result.rewards[i]/1e18 } FLUX on pool ${result.stakePools[i]}`);   
}

```
