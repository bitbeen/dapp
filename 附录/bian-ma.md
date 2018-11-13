## 合约
```
pragma solidity ^0.4.22;

contract Test{
    
    function sany(address _from,address _to,uint256 _value) returns(bytes32 sigdata){
        sigdata=keccak256(_from,_to,_value);
    }
    
}

```
## 客户端编码