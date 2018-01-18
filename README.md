# Pre-requisites

```
gem install msgpack
```

Having [dns_one](https://github.com/tomlobato/dns_one) installed and working, run the folowing command to make sure it is generating the stats properly:

```
dns_one stats
```

If you get an output like this you are ready to run munin-dnsone:

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
/etc/init.d/munin-node restart
```
