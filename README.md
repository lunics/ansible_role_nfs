# NFS Ansible role

Add this list to share a directory server side
```
nfs_exports:
  - "/srv/nfs/share        192.168.10.1/24(rw,sync,subtree_check,all_squash)"
```

Add this list to mount a remote nfs shared, [see](https://github.com/lunics/ansible_role_nfs/blob/public/defaults/main.yml)
```
nfs_imports:
  - local_path:  /path/share_dir
    remote_path: /srv/nfs/share
    server_host: 192.168.1.32 or hostname
    state: mounted              # optional
```

#### Todo
- [ ] Add "state" to nfs exports
- [ ] Template nfs.conf
