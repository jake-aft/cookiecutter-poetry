# BLX Pre-Commit Hooks Repo

This will need to automatically be updated with the latest version of the pre-commit hooks and tested

#### Add a precommit hook to parent project to auto update the pre-commit hooks when the pre-commit hooks repo is updated

**Options:**

- Space Automation on push to pre-commit hooks repo pushes to all repos and updates the submodule
  - this then triggers the pre-commit hooks to run in all repos on the next pull/push Might be the same as the last option
- Space Automation on push to parent repo updates the submodule to the latest version of the pre-commit hooks repo
- Space Automation on push to parent repo and there has been a change to the pre-commit hooks repo

## Adding as a submodule

- A git submodule is a git repository that is embedded inside another git repository.
  This is useful for including another project inside your project

### Adding a submodule

This command takes two arguments:

- URL of the submodule repository
- path where the submodule should be in the destination project

#### **_Example:_**

**TODO:** Check what we need in the Space Automation as the REPO_URL

```bash
export PRECOMMIT_DEPLOY_REPO="ssh://git@git.jetbrains.space/biolexistx/style/precommit_deployment_config.git"
```

Add the the precommit*deploy project as a submodule in the blx_myapp project directory utilities
\*\*\_Ensure you are in the root directory of the project*\*\*

```bash
# ADD SUBMODULE
git submodule add $PRECOMMIT_DEPLOY_REPO z_utilities/precommit_deploy
# OR UPDATE SUBMODULE
git submodule update --init --recursive
```
