To search through all branches of a git repo for a string, use:

```
$ git grep Linux $(git rev-list --all)

bxxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'PRD-AUE-LinuxAgents'
bxxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:          pool: 'PRD-AUE-LinuxAgents'
bxxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'PRD-AUE-LinuxAgents'
bxxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'PRD-AUE-LinuxAgents'
1xxxxxxxxxxxxxxx9:tf-pl-aue-prd-test.yml:        pool: 'PRD-AUE-LinuxAgents'
1xxxxxxxxxxxxxxx9:tf-pl-aue-prd-test.yml:          pool: 'AUE-LinuxAgents-PPD' 
1xxxxxxxxxxxxxxx9:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD' 
1xxxxxxxxxxxxxxx9:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD'
2xxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD'
2xxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:          pool: 'AUE-LinuxAgents-PPD' 
2xxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD' 
2xxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD'
bxxxxxxxxxxxxxxxd:tf-pl-aue-prd-test.yml:        pool: 'PPD-AUE-LinuxAgents'
```
To search through all branches ignoring string case:

```
$ git grep -i linux $(git rev-list --all)

bxxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'PRD-AUE-LinuxAgents'
bxxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:          pool: 'PRD-AUE-LinuxAgents'
bxxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'PRD-AUE-LinuxAgents'
bxxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'PRD-AUE-LinuxAgents'
1xxxxxxxxxxxxxxx9:tf-pl-aue-prd-test.yml:        pool: 'PRD-AUE-LinuxAgents'
1xxxxxxxxxxxxxxx9:tf-pl-aue-prd-test.yml:          pool: 'AUE-LinuxAgents-PPD' 
1xxxxxxxxxxxxxxx9:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD' 
1xxxxxxxxxxxxxxx9:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD'
2xxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD'
2xxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:          pool: 'AUE-LinuxAgents-PPD' 
2xxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD' 
2xxxxxxxxxxxxxxx3:tf-pl-aue-prd-test.yml:        pool: 'AUE-LinuxAgents-PPD'
bxxxxxxxxxxxxxxxd:tf-pl-aue-prd-test.yml:        pool: 'PPD-AUE-LinuxAgents'
```
This can also be done with regular expressions:
```
$ git grep -i RegEx $(git rev-list --all)
```
