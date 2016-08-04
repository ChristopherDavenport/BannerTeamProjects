# Advanced Git For Upstream Handling

Eckerd College Main Repository -> upstream
Personal Repository -> origin

1. First Fork Eckerd Colleges Repository - This creates your own version of the repository
2. Clone the repository to the location you would like to work on it
```
git clone ${LINK_TO_PERSONAL_REPOSITORY}
```
3. Say there are branches on the remote that do not exists on your personal copy. You need to pull those branches from your personal remote to your local copy.
``` 
git checkout --track origin/${BRANCH_NAME} 
```

3. Now lets say changes have been commited to the main repository that you would like to see reflected in your local repository. First we need to attach the primary as an upstream
```
git remote add upstream ${LINK_TO_ECKERD_REPOSITORY}
git fetch upstream
```
This created two local branches that represent the upstream copies that you can pull in. As we would like only to advance the work rather than create a merge commit we choose not to use the --no-ff. 

First make sure you are on the branch you would like to advance, and then merge in the changes.
```
git checkout develop
git merge upstream/develop
```

This would work with other branches as well. So now you can stay in sync from upstream repositories. No deleting just yanking yourself forward.
