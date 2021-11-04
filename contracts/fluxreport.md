# FluxReport

### getLoanPoolReport

Search all  loan pool inforamation.

```solidity
struct LoanPoolReport {
        address pool; //借贷池合约地址
        uint256 tvl; // TVL=总存款
        uint256 totalSupply; //总存款数量
        uint256 totalBorrow; //总借款数量
        uint256 priceUSD; //资产价格
        uint256 supplyInterestPreDay; //存款日利率
        uint256 borrowInterestPreDay; //借款日利率
        uint256 supplyFluxAPY; // 存款 FLUX年化收益率
        uint256 borrowFluxAPY; // 借款 FLUX年化收益率
        address underlying; //底层资产地址
}

function getLoanPoolReport() public view returns ([] memory pools)
```

### getStakePoolReport

Search all stake pool information.

```solidity
struct StakePoolReport {
        address pool; //抵押池合约地址
        uint256 tvl; //抵押池TVL
        uint256 apy; //抵押池FLUX产出年化收益率
        address token0; //抵押池对应资产token0
        address token1; //抵押池对应资产token1
        uint256 token0Staked; //抵押池对应资产token0质押数量
        uint256 token1Staked; //抵押池对应资产token1质押数量
        uint256 token0PriceUSD; // token0 价格
        uint256 token1PriceUSD; // token1 价格
    }

function getStakePoolReport() public view returns (StakePoolReport[])
```
