Useful Git Aliases


### When Using Forks and Upstreams

    # Simple wrapper for fetching all upstream, then rebasing the given branch. Use before you push as well
    up = pull --rebase upstream master

    # Rebases on the given fork & branch; for preparing a PR
    ready = rebase -i @{u}

    # Forces Pushes branch to Origin
    done = "!f() { git push --force-with-lease origin $@; }; f"
    
    # Sets the current working branch to an upstream
    publish = "!git push --set-upstream origin \"$(git rev-parse --abbrev-ref HEAD)\""
    
### Viewing Logs

    l = log
    ll = log --decorate --oneline --graph
    lll = log --decorate --graph --abbrev-commit --date=relative
    
    # Whats in my HEAD, that is not in my upstream. Useful, when wanting to know what commits to rebase/squash
    lu = log @{u}..HEAD
    
### General
    # always rebase to avoid merge commit messages
    p = pull --rebase
    
    # pull --rebase and push - a nice shortcut to use instead of git push that can fail
    pp = "!git pull --rebase && git push"

