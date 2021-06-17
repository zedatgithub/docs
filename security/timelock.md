# 🔥 Timelock

Timelock will been added to the MasterChef contract before launch.

Timelock address: [0xe6a8f0269d6af307a908ecd3938f470db7a56daa](https://bscscan.com/address/0xe6a8f0269d6af307a908ecd3938f470db7a56daa)

Ownership transfer transaction:  
[0x9691ea4a9455ebfbb47b890d296acd4a00e626475d83db65ee41e36d00f90d0f](https://bscscan.com/tx/0x9691ea4a9455ebfbb47b890d296acd4a00e626475d83db65ee41e36d00f90d0f)​​

{% hint style="info" %}
Delay: **24 hours** from the start
{% endhint %}

> Note that in the [MasterChef](https://bscscan.com/address/0x) contract we have **4 functions** which we can call outside the timelock.   
> We use these for adding more pools, updating existing pools and updating the emission rates without having to wait for 24 hours for the changes to propagate.

{% code title="MasterChef.sol" %}
```javascript
// Update the MasterChef address. Can only be called by the admin.
function updateMasterChef(IMasterChef _MasterChef) public {
    require(msg.sender == admin, "Timelock::updateMasterChef: Call must come from admin.");
    MasterChef = _MasterChef;
}

// Add a new lp to the pool. Can only be called by the admin.
function add(uint256 _allocPoint, IBEP20 _lpToken, uint16 _depositFeeBP, uint256 _harvestInterval, bool _withUpdate, uint256 _allocPointSecondary) public {
    require(msg.sender == admin, "Timelock::add: Call must come from admin.");
    MasterChef.add(_allocPoint, _lpToken, _depositFeeBP, _harvestInterval, _withUpdate, _allocPointSecondary);
}

// Update the given pool's Pancake allocation point and deposit fee. Can only be called by the admin.
function set(uint256 _pid, uint256 _allocPoint, uint16 _depositFeeBP, uint256 _harvestInterval, bool _withUpdate, uint256 _allocPointSecondary) public {
    require(msg.sender == admin, "Timelock::set: Call must come from admin.");
    MasterChef.set(_pid, _allocPoint, _depositFeeBP, _harvestInterval, _withUpdate, _allocPointSecondary);
}

// Update the emission rate. Can only be called by the admin.
function updateEmissionRate(uint256 _pancakePerBlock) public {
    require(msg.sender == admin, "Timelock::updateEmissionRate: Call must come from admin.");
    MasterChef.updateEmissionRate(_pancakePerBlock);
}
```
{% endcode %}



