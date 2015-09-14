# git-promote
git extension to squash merge pull requests into master

This is a git extension that squash merges a pull request into the master
branch. The process is as follows:

```sh
git promote <PR_NUM>
```

1. `git pull origin pull/$PR_NUM/head:pullrequest-$PR_NUM`
2. `git checkout pullrequest-$PR_NUM`
3. `git pull origin master`
4. `git checkout master`
5. `git merge --squash pullrequest-$PR_NUM`
6. `git commit`
7. `git push origin master`
8. `git branch -D pullrequest-$PR_NUM`

## Installation

You can install git-promote using npm install.
```sh
npm install -g git-promote
```

## License

[The MIT License (MIT)](http://opensource.org/licenses/mit-license.php)
