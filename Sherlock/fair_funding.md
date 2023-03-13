
## Info
 - ref: https://app.sherlock.xyz/audits/contests/42

<br>

------

# Operators can add and remove other operators causing a privilege escalation on the contract Vault

## Summary
An operator can add and remove other operators.

## Vulnerability Detail
If an operator is compromised then this will permit him/her to add and remove other operators without their consent. This program behavior could be seen as a privilege escalation, as an operator might add other operators, but should not be able to remove them. To prove my point i give the following example: in a operating system a normal user can delete itself, but cannot delete another normal user, instead an admin user should be the only one who is able to do such operations. So the same may reflect on Vault contract and operators.

## Impact
The issue could be seen as privilege escalation, also we rank this vulnerability as high because of the issue https://github.com/sherlock-audit/2023-02-fair-funding-tin-z/issues/4 which might allow the attacker to be only operator.

## Code Snippet
https://github.com/sherlock-audit/2023-02-fair-funding/blob/main/fair-funding/contracts/Vault.vy#L604-L628

## Tool used
vim
Manual Review

## Recommendation
We suggest to permit only admin to add and or remove operators.
