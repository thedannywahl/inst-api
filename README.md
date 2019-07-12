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
The included scripts require the following dependencies.  The scripts will attempt to install `brew` dependencies if they're not found. System or built-in commands must be installed by the user.

### System / Built-in
* [curl](https://curl.haxx.se/)
* [sed](https://www.gnu.org/software/sed/)
* [cut](http://pubs.opengroup.org/onlinepubs/9699919799/utilities/cut.html)
* [grep](https://www.gnu.org/software/grep/)
* [getopts](http://pubs.opengroup.org/onlinepubs/9699919799/utilities/getopts.html)

### External
* [jq](https://stedolan.github.io/jq/) ([brew](https://brew.sh/))

## Security

### Credentials
All commands store credentials in a dot file in the user home directory, specifically `~/.inst` and they source the contents at runtime.  **DO NOT** store your tokens or credentials on a shared machine or user space.  If security is a concern, all commands allow you to pass credentials in via options at runtime using `-t <token>`, `-p <password>`, or the like.  Check the help documentation for the each command for specific details.  This allows you to use other credential managers like [vaulted](https://github.com/miquella/vaulted).  See help (`-h`) for more information with each command.

### Encryption
All `curl` commands will attempt to use the `--tlsv1.3` flag if supported, otherwise it will fall back to `--tlsv1.2`. If your machine does not support at least TLS v1.2, downgrade at your own risk. All paths explicitly start with `https`. Instructure products **WILL NOT** function over `http` except to redirect to `https`.  
