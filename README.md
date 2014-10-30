# munin-pm2

Munin plugin to monitor pm2. Written in javascript.

## about

This is a work in progress, at a very early stage.

Feel free to contribute.

## installation

On Debian :

 - put the plugin in `/usr/share/munin/plugins/`
 - create 3 symlinks to the plugin, named `pm2_cpu`, `pm2_memory` and `pm2_status` in `/etc/munin/plugins/`.
 - install the pm2 module in `/etc/munin/plugins/` with `npm install pm2`
 - see the [`options`](@options) section to configure the plugin to match your setup
 - restart munin-node

## options

You need to make the plugin run as the user who runs pm2.

On debian, here is what I have in `/etc/munin/plugin-conf.d/munin-node` :
```
[pm2_*]
user myuser
command sudo -u myuser %c
```

Please note that for me, setting the user was not enough, I had to override
the command too.
