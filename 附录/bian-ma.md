## 合约
```solidity
pragma solidity ^0.4.22;

contract Test{
    
    function sany(address _from,address _to,uint256 _value) returns(bytes32 sigdata){
        sigdata=keccak256(_from,_to,_value);
    }
    
}

```
## 客户端编码
```js
function solSha3 (...args) {
    args = args.map(arg => {
        if (typeof arg === 'string') {
            if (arg.substring(0, 2) === '0x') {
                return arg.slice(2)
            } else {
                return web3.utils.toHex(arg).slice(2)
            }
        }

        if (typeof arg === 'number') {
            return web3.utils.padLeft((arg).toString(16), 64, 0)
        } else {
            return ''
        }
    })

    args = args.join('')

    return web3.utils.sha3(args, { encoding: 'hex' })
}



```