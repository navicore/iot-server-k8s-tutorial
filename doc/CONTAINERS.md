IOT Server K8S Tutorial Extra Container Lab
---

### Container Lab

  From Jessie Frazelle talk http://containersummit.io/events/nyc-2016/videos/building-containers-in-pure-bash-and-c

  #### "namespaces" limit what a process sees

  * ns examples: pid, net, mnt, uts, ipc, user
  * find them in `/proc/{pid}/ns`
  * net ns
    * normal: `sudo ip a` clones your process and shows stuff in your net ns
    * container-like: `sudo unshare --net ip a` clones your process w/o net ns
  * uts ns
    * normal: `hostname`
    * container-like: `sudo unshare --uts -- /bin/bash -c 'hostname mycontainer && hostname'`
    * normal: `hostname` host hostname is unchanged
  * ipc ns
    * `ipcmk -Q` create a queue
    * normal: `ipcs -q` see queue(s)
    * container-like: `sudo unshare --ipc -- ipcs -q` new process can't see queue
  * user ns
    * normal: `ls -la`
    * container-like: `unshare --user -- ls -la` see nobody
  * mount ns (give process a rootfs)
  * pid ns (if you mound proc then you'll only see yourself and your children)

  #### "control groups" limit what a process can use
  * resource metering and limiting
  * types: memory, CPU, blkio, network, device

  ### Learn more about containers, rootless priv, and supervision by playing wth [runc](https://github.com/opencontainers/runc)
  
