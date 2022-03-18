## Verifying Release Packages

This repo contains the raw release signing keys in two forms:

 1. The **keys/** directory contains the raw ASCII-armored release signing keys listed above.

 2. The **gpg/** directory contains a GPG keyring preloaded with these release signing keys.

For additional verification of both the keys' content *and* of the list of authorized signing
keys, you may cross-reference the list with [nodejs.org](https://nodejs.org) and attempt to
fetch keys from alternative sources (instead of or in addition to this repo).

### Using the preloaded GPG keyring

First, clone this repo:

```bash
git clone https://github.com/nodejs/release-keys.git
```

Then, prefix your `gpg` commands with the path to the cloned repo's **gpg/** directory.
For example, if you cloned the repo to **/path/to/nodejs-keys**, then the `gpg` command
to verify a release package will look something like this:

```bash
GNUPGHOME=/path/to/release-keys/gpg gpg --verify SHASUMS256.txt.sig SHASUMS256.txt
```

### Using your own GPG keyring

First, clone this repo:

```bash
git clone https://github.com/nodejs/release-keys.git
```

Then, import the release signing keys from this repo into your GPG keychain by invoking
the **cli.sh** script in this repo. For example, immediately after cloning the repo above,
the following command will import all release signing keys:

```bash
release-keys/cli.sh import
```
