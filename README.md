# dot-ansible
re-implementation of setup/install scripts from dotfiles, redone in ansible


## usage

```
ansible-playbooks main.yml --ask-become-pass
```

The variables in `main.yml` (at the top of the file) need to be set to whatever values are specific to you.
Edit those values (or pass them in as variables in the command line) in the file, save the file, and run
the commands above.

More instructions soon to come.
