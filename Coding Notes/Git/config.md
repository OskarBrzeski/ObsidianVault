```bash
git config <option> <config-name> <value>
```
Configure name and email
```bash
git config user.name "Full Name"
git config user.email "email@provider.com"
```
Configure default text editor
```bash
git config core.editor "nvim"
```
Store credentials
```bash
git config credential.helper store
git push  # Enter credentials
```
Set timeout for credentials
```bash
git config credential.helper "cache --timeout <time-in-s>"
```
Set default branch name
```bash
git config init.defaultBranch "main"
```
## Options
**`--local`** 
- Configure setting for current git repository.
- Stored in `./.git/config`.
- Default behaviour.
**`--global`**
- Configure setting for current user.
- Stored in `~/.gitconfig` or `$XDG_CONFIG_HOME/git/config`.
**`--system`**
- Configure setting for current system.
- Stored in `/etc/gitconfig`.