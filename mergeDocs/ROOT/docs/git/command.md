## Git Environment Setup

## Setting username
```bash
git config --global user.name "Roy.chan"  
```

## Setting email id
```bash
git config --global user.email  "w983874@gmail.com"
```

## Setting editor
```bash
git config --global core.editor Vim
```

## Checking Your Settings listed
```bash
git config --list
```

## Git configuration levels
- local
- global
- system

### local
- default level in Git
- Git config will write to a local level
- values are stored in .git/config directory as a file.

### global
- The global level configuration is user-specific configuration ,which is `applied to an individual operating system user`.
- Global configuration `values` are stored in `user's home directory`.. ~ /.gitconfig

### system
- is applied across an entire system means all users on `an operating system and all repositories`.
- stores in a gitconfig file of the `$(prefix)/etc/gitconfig` on UNIX and `C:\ProgramData\Git\config` on Windows