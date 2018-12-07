# SubPixelPerfect



To push as different user  [link](https://medium.com/@bivil/you-can-configure-an-individual-repo-to-use-a-specific-user-email-address-which-overrides-the-6e5f6521d5c9)

```bash
cd "git/root"
# set different user info
git config user.name "Your Name1"
git config user.email your@email1.com

#or using editor
git config -e

# ensure that local and global values are different
git config --local -l
git config --global -l
```

