---
layout: default
title: SSH Key Permissions
---

# SSH Key Permissions

Proper file permissions help keep your SSH keys secure. On most systems,
you can set permissions using `chmod`:

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
```

* `~/.ssh` directory should be readable, writable and executable only by
  you (`700`).
* Your private key (e.g. `id_rsa`) should be readable and writable only by
  you (`600`).
* The public key can be world-readable (`644`).

[Back to home]({{ '/' | relative_url }})
