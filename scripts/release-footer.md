### Verifying signatures

The releases are signed by Nadav Ivgi (@shesek). The public key can be verified on the [PGP WoT](http://keys.gnupg.net/pks/lookup?op=vindex&fingerprint=on&search=0x81F6104CD0F150FC), [github](https://api.github.com/users/shesek/gpg_keys), [twitter](https://twitter.com/shesek), [keybase](https://keybase.io/nadav), [hacker news](https://news.ycombinator.com/user?id=nadaviv) and [this video presentation](https://youtu.be/SXJaN2T3M10?t=4).

```bash
# Download (change x86_64-linux to your platform)
$ wget https://github.com/bwt-dev/libbwt-jni/releases/download/v0.2.1/libbwt-jni-0.2.1-x86_64-linux.tar.gz

# Fetch public key
$ gpg --keyserver keyserver.ubuntu.com --recv-keys FCF19B67866562F08A43AAD681F6104CD0F150FC

# Verify signature
$ wget -qO - https://github.com/bwt-dev/libbwt-jni/releases/download/v0.2.1/SHA256SUMS.asc \
  | gpg --decrypt - | grep x86_64-linux.tar.gz | sha256sum -c -
```

The signature verification should show `Good signature from "Nadav Ivgi <nadav@shesek.info>" ... Primary key fingerprint: FCF1 9B67 ...` and `libbwt-jni-0.2.1-x86_64-linux.tar.gz: OK`.

### Reproducible builds

The builds are fully reproducible.

You can verify the checksums against the v0.2.1 builds on Travis CI: https://travis-ci.org/github/bwt-dev/libbwt-jni/builds/

See [more details here](https://github.com/bwt-dev/libbwt-jni#reproducible-builds).
