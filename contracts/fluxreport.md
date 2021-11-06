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

### getLoanPoolMeta

Search market information and user loan info with given loan pool.

```solidity
struct MarketMeta {
        // user info
        uint256 userBorrowings;
        uint256 userDeposits;
        uint256 userUnderlyingAllowance;
        uint256 userUnderlyingBalance;
        uint256 userBorrowLimit;
        uint256 userWithdrawLimit;
        // token info
        address underlying;
        uint256 underlyingPrice;
        //config
        uint256 borrowCap;
        uint256 reserveFactor;
        uint256 maxinumLTVRatio;
        // market data
        uint256 ftokenSupply;
        uint256 totalBorrows;
        uint256 liquidity;
        uint256 exchangeRate;
        uint256 borrowAPY;
        uint256 depositAPY;
        uint256 depositDistributionFluxAPY;
        uint256 borrowDistributionFluxAPY;
        uint256 decimals;
    }

    /**
      @notice search market information and user loan info with given market.
      @dev user loan info is zero if `user` is empty.
     */
function getLoanPoolMeta(address mkt, address user) external view returns (MarketMeta memory meta) {
    
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

### getAllStakeMeta

Search all stake pool information and user stake info.

```solidity
struct StakeMeta {
    address pool;
    uint256 staked;
    uint256 tokenAllownce;
    uint256 tokenBalance;
    address token;
    uint8 tokenDecimals;
    StakePoolReport poolMeta;
}

function getAllStakeMeta(address user) external view returns (StakeMeta[] memory pools)
```
