# Git flow

### Main Branches

- 📝 **master or main** - release for production (stable code) --> version tag here
- 🎨 **develop** - develop base to feature branch

### Supporting Branches

- 🧑‍💻 **feature** - develop new feature from branch develop --> this will merge to develop branch after done.
- 🤹 **release** - create release from develop for deploy to dev for staging environment. Tester, QA test afterwards merge into master and develop.
- 🎥 **hotfix** - if issue from release will create new branch from master to hotfix afterwards merge back in to master and develop

[Docs](https://github.com/nvie/gitflow)
