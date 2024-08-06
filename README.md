# infra
Infrastructure as code (IaC) for my personal infrastructure.

## Important Disclaimer
The contents of this repo are not recommended for use by anyone, since it is opinionated, minimally viable, may omit or assume additional undocumented and manual security configuration, and is specific to the hardware and services that I own and manage.  This repo is also very much a work in progress and subject to breaking changes and refactoring, although presumptively not so much that I break my own services.  That said, this repo may be useful as a reference for those wanting to manage their own home lab.

## Requirements
For local machines, install the latest Debian stable distribution (e.g. Debian 12 "Bookworm", at the time of this writing) using expert mode, and following best practices, with one non-root administration user.

### Manually preparing local target hosts
1. Add management SSH key(s) to the authorized_keys file of the sudo administration user that was added during operating system installation, by logging in with that user
```
mkdir ~/.ssh
touch ~/.ssh/authorized_keys
vi  ~/.ssh/authorized_keys # add management keys
chmod 400 ~/.ssh/authorized_keys
chmod 700 ~/.ssh/
```

2. Add the administration user to the end of the sudoers file
```
sudo vi /etc/sudoers # add this line: sysop ALL=(ALL) NOPASSWD: ALL
```

### Decision Log
Debian Linux was chosen because the latest Red Hat distribution, and all derivative distributions, no longer support older Intel instruction set extensions required by some very old hardware.

## License
Apache License (Version 2.0)
