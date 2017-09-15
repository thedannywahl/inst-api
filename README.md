Elaborate curl wrappers for Instructure product APIs.

## Installation

### Homebrew
Once [homebrew](https://brew.sh/) is installed, run the following:

```
brew tap thedannywahl/inst-api
brew install inst-api
```

### Download

[Download](https://github.com/thedannywahl/inst-api/releases) or clone the latest release and symlink the scripts to a location supported in your `$PATH`

## Dependencies
Your system needs the following dependencies.  The programs will attempt to install `npm` and `pip` dependencies on first run if they're not found. System or built-in commands must be installed by the user.

### System / Built-in
* [curl](https://curl.haxx.se/)
* [sed](https://www.gnu.org/software/sed/)
* [cut](http://pubs.opengroup.org/onlinepubs/9699919799/utilities/cut.html)
* [getopts](http://pubs.opengroup.org/onlinepubs/9699919799/utilities/getopts.html)

### External
* [json](https://www.npmjs.com/package/json) ([npm](https://www.npmjs.com/))
* [pygments](http://pygments.org/) ([pip](https://pypi.python.org/pypi))

## Security

### Credentials
All commands store credentials in a dot file in your home directory, specifically `~/.inst` and they source the contents at runtime.  **DO NOT** store your tokens or credentials on a shared machine.  If security is a concern, all commands allow you to pass credentials in via options at runtime using `-t <token>` or `-p <password>`.  This allows you to use other credential managers like [vaulted](https://github.com/miquella/vaulted).  See help (`-h`) for more information with each command.

### Encryption
All curl commands use the `--tlsv1.2` flag and all paths explicitly start with `https`.  If your machine does not support TLS v1.2, downgrade at your own risk.  Instructure products **WILL NOT** function over `http` except to redirect to `https`.  
