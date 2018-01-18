# Pre-requisites

```
gem install msgpack
```

Having [dns_one](https://github.com/tomlobato/dns_one) installed and working, run this to make sure it is generating stats:

```
dns_one stats
```

If you ge a an output like this you are ready to run munin-dnsone:

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
```
wget https://raw.githubusercontent.com/tomlobato/munin-dnsone/master/dnsone_munin_ -O /usr/local/sbin/dnsone_munin_
chmod 755 /usr/local/sbin/dnsone_munin_
dnsone_munin_ install
/etc/init.d/munin-node restart
```
