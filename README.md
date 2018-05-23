# munin-hbase
Munin plugin for monitoring global HBase status

Uses `hbase` shell to get cluster statistics 

Monitored data:
 * requests per second
 * used heap
 * read requests count
 * write requests count

## usage
Copy `hbase` file to Munin plugins folder, for ex. `/usr/local/share/munin/plugins`

Symlink this file into `/etc/munin/plugins` once per series.
Example:
```
ln -s /usr/local/share/munin/plugins/hbase /etc/munin/plugins/hbase_requestsPerSecond
ln -s /usr/local/share/munin/plugins/hbase /etc/munin/plugins/hbase_usedHeap
ln -s /usr/local/share/munin/plugins/hbase /etc/munin/plugins/hbase_readRequestsCount
ln -s /usr/local/share/munin/plugins/hbase /etc/munin/plugins/hbase_writeRequestsCount
```

Copy and edit if needed default configuration file `hbase.conf` to `/etc/munin/plugins-conf.d/hbase`

Restart `munin-node`

## configuration
Only HBase user and full path of `hbase` binary are needed.
Example:
```
[hbase*]
user hbase
env.hbasebinary /usr/local/hbase/bin/hbase
```
