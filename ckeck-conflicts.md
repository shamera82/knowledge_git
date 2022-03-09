```bash
AzureAD+ShameraRanathunga@LAB3-PF336A6J MINGW64 ~/git/personal/aws/terraform (master|MERGING)
$ git push
To https://github.com/shamera82/terraform.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/shamera82/terraform.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

AzureAD+ShameraRanathunga@LAB3-PF336A6J MINGW64 ~/git/personal/aws/terraform (master|MERGING)
$ git pull
error: Pulling is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

AzureAD+ShameraRanathunga@LAB3-PF336A6J MINGW64 ~/git/personal/aws/terraform (master|MERGING)
$ git diff --name-only --diff-filter=U
aws/ec2/sample_output.md

AzureAD+ShameraRanathunga@LAB3-PF336A6J MINGW64 ~/git/personal/aws/terraform (master|MERGING)
$ git diff --check

AzureAD+ShameraRanathunga@LAB3-PF336A6J MINGW64 ~/git/personal/aws/terraform (master|MERGING)
$ git config --global alias.conflicts '!git ls-files -u | cut -f 2 | sort -u'

AzureAD+ShameraRanathunga@LAB3-PF336A6J MINGW64 ~/git/personal/aws/terraform (master|MERGING)
$ git conflicts
aws/ec2/sample_output.md

AzureAD+ShameraRanathunga@LAB3-PF336A6J MINGW64 ~/git/personal/aws/terraform (master|MERGING)
$
```
