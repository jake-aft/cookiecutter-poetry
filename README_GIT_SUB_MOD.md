# BLX Pre-Commit Hooks  Repo

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

#### ***Example:***

**TODO:** Check what we need in the Space Automation as the REPO_URL

```bash
export PRECOMMIT_REPO_URL="https://git.jetbrains.space/biolexistx/style/precommit_deployment_config.git"
# OR if we need SSH
export PRECOMMIT_DEPLOY_REPO_SSH="ssh://git@git.jetbrains.space/biolexistx/style/precommit_deployment_config.git"
# OR Maybe more like this
export PRECOMMIT_DEPLOY_REPO="URL or SSH AS ABOVE"
```
Add the the precommit_deploy project as a submodule in the blx_myapp project directory utilities
```bash
git submodule add $PRECOMMIT_DEPLOY_REPO_URL blx_myapp/z_utilities/precommit_deploy
git submodule add $PRECOMMIT_DEPLOY_REPO_SSH blx_myapp/z_utilities/precommit_deploy
git submodule add $PRECOMMIT_DEPLOY_REPO z_utilities/precommit_deploy
```
### Update the submodule
***Update the submodules happens automatically when you run:***
```bash
git submodule update --init --recursive
```