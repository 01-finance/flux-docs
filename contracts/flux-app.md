# Flux App

### getAcctSnapshot

search given address's loan infomation that includes supply,borrow and borrow limit。

```solidity
/**
     * @notice 查询账户借贷信息
     * @dev 一次性查询指定账户的借贷信息
     * @param acct 待查询账户
     * @return supplyValueMan uint256 存款额（尾数）
     * @return borrowValueMan uint256 借款额（尾数）
     * @return borrowLimitMan uint256 所需要的抵押额（尾数）
     */
 function getAcctSnapshot(address acct)
    public
        view
        returns (
            uint256 supplyValueMan,
            uint256 borrowValueMan,
            uint256 borrowLimitMan
        );
```

* deposits (USD) =  supplyValueMan/1e18
* borrowings (USD) = borrowValueMan/1e18
* borrowPower (USD) =  borrowLimitMan /1e18
* borrowPowerUsed =  min(borrowings/ borrowPower \* 100%,100%)
* healthFactor = borrowings/ depositis \* 100%

