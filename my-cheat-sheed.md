## Configuration
### For global setup

```
## this will effect all folders in you machine
git config --global user.email <github email>`

git config --global user.name <github username>
```

### For local setup
```
git config --local user.email <github email>

git config --local user.name <github username>

```
### Basic workflow
```
git status

git add .

git commit

#### use VIM, otherwise it's war

git push <remote> <branch>
```


## Review workflow by fetching the branch locally
### Add the remote of the PR
`git remote add <remote_name> <remote_url>`

`git fetch <remote_name>`


