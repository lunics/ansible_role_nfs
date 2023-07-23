# Ansible role: NFS

Only tested on Archlinux.

### Examples:
Override [defaults](https://github.com/lunics/ansible_role_nfs/blob/main/defaults/main.yml)
```yaml
# Add this list to share a directory, server side
nfs_exports:
  - "/srv/nfs/share        192.168.10.1/24(rw,sync,subtree_check,all_squash)"

# Add this list to mount a remote nfs shared, client side
nfs_imports:
  - local_path:  /path/share_dir
    remote_path: /srv/nfs/share
    server_host: 192.168.1.32 or hostname
    state:       mounted         # optional
```

---
This role is a mix of these repos:
- [geerlingguy](https://github.com/geerlingguy/ansible-role-nfs)
- [ome](https://github.com/ome/ansible-role-nfs-mount)
- [indigo-dc](https://github.com/indigo-dc/ansible-role-nfs)
---

#### Todo:
- [ ] Add compatibility for RHEL, Debian
- [ ] Add "state" to nfs exports
- [ ] Template nfs.conf
