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
