# Security Tags
## Explanation 
Security tags are a standard for auditing methods against common security issues, they piggy back off the existing **@see** tag in popular documentation generators such as Javadoc and PHPDoc, to that extent it should be considered language agnostic.
## Example 
```
/**
 * @see https://github.com/AlexanderDS/security-tags/ SC-V1-L1-111X111
 */
```
## Structure 
The struture of a security tag is as follows:
```
{namespace:string}-{version:string}-{level:string}-{scores:string}
```
Scores can be made up of one of 3 characters
* **0** Fail
* **1** Pass
* **X** Not applicable

## Passing Audits
A method can be considered to pass the security audit when its tag score is made up of all 1's or X's, a 0 anywhere is a fail.

**Best Practice:** When generating security tags for your chosen version and level you should ALWAYS set all scores as **0** this will ensure that you are actively performing the audit on your method to know with certainty that it passes or is not applicable.
 
# Version 1 :: DRAFT
This version is currently being worked on and should not be used in any comments as the scores within each level may change order or number of security checks. Additionally full defnitions as to what each check is doing may be incomplete.
 
## Level 1 - Permissions [1,2,3,4,5,6,7]
```
@see https://github.com/AlexanderDS/security-tags/ SC-V1-L1-0000000
```
Level 1 is concerned with methods being used only in the correct circumstances, i.e by an authorized user with all the correct rights dealing only with the known parameters of the method.
 
1. Enforces Create rights
2. Enforces Read rights
3. Enforces Update rights
4. Enforces Delete rights
5. Cross-resource protection
6. Expected parameters only
7. Expected values only

## Level 2 - Data Input [1,2,3]
```
@see https://github.com/AlexanderDS/security-tags/ SC-V1-L2-000
```
Level 2 is about the data coming into your method to make sure it's within allowable/expected parameters.

1. Enforce data types
2. Whitelist only expected inputs (i.e. original options of multiple choice data or accpetable ranges for numeric)
3. Blacklist known bad or unwated elements

**Note:** you may want to check string input against [Big List of Naughty Strings](https://github.com/minimaxir/big-list-of-naughty-strings)

## Level 3 - Data Output [1,2]
```
@see https://github.com/AlexanderDS/security-tags/ SC-V1-L3-00
```
Level 3 protects data from being harmful even if it was previously

1. Enforce data types
2. Filter string data as approritate

## Level 4 - Database Interaction [1,2]
```
@see https://github.com/AlexanderDS/security-tags/ SC-V1-L4-00
```
Level 4 protects your database

1. Enforce data types
2. Rely on stored procedures only


