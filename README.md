# Pre-requisites

```
gem install msgpack
```

# Check your [DnsOne](https://github.com/tomlobato/dns_one) instalation

Run the folowing command to verify if dns_one is exporting its stats properly:

```
dns_one stats
```

If you get an output like this you are ready to install munin-dnsone:

```
--- rcode ---
no_error	10
nx_domain	2
--- req_resource ---
a	12
--- cache ---
miss	4
hit	8
```

# Install

As root, run:

```
wget https://raw.githubusercontent.com/tomlobato/munin-dnsone/master/dnsone_munin_
chmod 755 dnsone_munin_
mv dnsone_munin_ /usr/local/sbin/
dnsone_munin_ install
```

Then test:

```
munin-run dnsone_cache config
munin-run dnsone_cache

munin-run dnsone_rcode config
munin-run dnsone_rcode

munin-run dnsone_req_resource config
munin-run dnsone_req_resource

munin-run dnsone_requests config
munin-run dnsone_requests
```

If you get an output like this, you are ready to go just restart munon-node:

```
/etc/init.d/munin-node restart
```


