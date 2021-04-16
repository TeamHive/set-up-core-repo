# set-up-core-repo

This action will help setup a project using `@teamhive/core packages`. It assists in installing dependencies from cache, installing the `@teamhive/core-cli` and installing any other packages that contain private actions on the `@teamhive/core-actions-common` framework.

**Note:** While this action is public do to requirements for composite GitHub Actions it probably won't be helpful for any projects outside of those within the TeamHive Organization. The main benefit of this action is to facilitate installing `@teamhive/core` dependencies, which are not public packages.

## Inputs

| Input                  | Description                                                                                                                                                                                                                                       |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `install-dependencies` | If true, the action will install yarn dependencies. Uses the package.json/yarn.lock file to install dependencies. If this is true, the package.json should include the `@teamhive/core-cli` and any other action packages you wish to initialize. |
| `from-cache`           | If true, the action will restore the dependencies from cache.                                                                                                                                                                                     |
| `action-packages`      | Comma separated value string of teamhive action packages to set-up. If `install-dependencies` is disabled these will be globally installed alongside the `@teamhive/core-cli`.                                                                    |

## Outputs

| Input               | Description                                                                                |
| ------------------- | ------------------------------------------------------------------------------------------ |
| `primary-cache-key` | If dependencies were restored/saved to cache, this is the primary cache key that was used. |
| `cache-hit`         | If cache was restored, this indicates if the cache hit was an exact match                  |
