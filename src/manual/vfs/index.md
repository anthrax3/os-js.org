---
title: VFS
layout: layout.html
---

# VFS

The *Virtual File System* is an abstraction layer that allows you to connect to any source (or endpoint) and present it as it was a file or directory to OS.js.

Modules known as *Transports* handles the incoming requests and responses. These are linked to a *Mountpoint* that is shown in OS.js.

## Mountpoints

To create your own mountpoints you can use the included configuration tool:

```bash
# Add with the built in shortcut
grunt config:add-mount --name=data --description="My data files" --path=/tmp

# Update configuration
grunt build:config
```

This will create the mountpoint `data://` and points to `/tmp` on the server. For group permissions, see [here](/manual/auth/permission).

You can set it to read-only by using:

```json
{
  "server": {
    "vfs": {
      "mounts": {
        "data": {
          "ro": true,
          "destination": "/tmp"
        }
      }
    }
  }
}
```

*Better CLI configuration support coming soon*