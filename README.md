# munin-hbase
Munin plugin for monitoring global HBase status

Uses `hbase` shell to get cluster statistics 

Monitored data:
 * requests per second
 * read requests per second
 * write requests per second
 * heap usage
 * uncompressed data volume

## usage
Copy `hbase-multigraph` file to Munin plugins folder, for ex. `/usr/local/share/munin/plugins`

Symlink this file to `/etc/munin/plugins`

Copy or symlink, and edit if needed, default configuration file `hbase.conf` to `/etc/munin/plugins-conf.d/hbase`

Restart `munin-node`

## configuration
Only HBase user and full path of `hbase` binary are needed.
Example:
```
[hbase*]
user hdfs
env.hbasebinary /usr/local/hbase/bin/hbase
```
