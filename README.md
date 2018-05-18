# Pre-requisites

```
gem install msgpack
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

If you get an output like this, you are ready to go, just restart munin-node with ```/etc/init.d/munin-node restart```
:

```
graph_category DnsOne
graph_title cache
graph_vlabel %
graph_args --base 1000 -l 0
hit.label hit
miss.label miss

hit.value 95.2
miss.value 4.8


graph_category DnsOne
graph_title rcode
graph_vlabel %
graph_args --base 1000 -l 0
badalg.label badalg
badkey.label badkey
badmode.label badmode
badname.label badname
badsig.label badsig
badtime.label badtime
badvers.label badvers
form_err.label form_err
no_error.label no_error
not_auth.label not_auth
not_imp.label not_imp
not_zone.label not_zone
nx_domain.label nx_domain
nxrr_set.label nxrr_set
refused.label refused
serv_fail.label serv_fail
yx_domain.label yx_domain
yxrr_set.label yxrr_set

badalg.value 0.0
badkey.value 0.0
badmode.value 0.0
badname.value 0.0
badsig.value 0.0
badtime.value 0.0
badvers.value 0.0
form_err.value 0.0
no_error.value 96.15912208504801
not_auth.value 0.0
not_imp.value 0.0
not_zone.value 0.0
nx_domain.value 3.840877914951989
nxrr_set.value 0.0
refused.value 0.0
serv_fail.value 0.0
yx_domain.value 0.0
yxrr_set.value 0.0


graph_category DnsOne
graph_title req_resource
graph_vlabel %
graph_args --base 1000 -l 0
a.label a
aaaa.label aaaa
any.label any
cname.label cname
hinfo.label hinfo
minfo.label minfo
mx.label mx
ns.label ns
ptr.label ptr
soa.label soa
txt.label txt
wks.label wks

a.value 52.64663805436338
aaaa.value 28.755364806866954
any.value 0.0
cname.value 0.0
hinfo.value 0.0
minfo.value 0.0
mx.value 6.294706723891274
ns.value 2.575107296137339
ptr.value 0.0
soa.value 4.577968526466381
txt.value 4.86409155937053
wks.value 0.0


graph_category DnsOne
graph_title requests
graph_vlabel requests / second
graph_args --base 1000 -l 0
requests.label requests

requests.value 1.8366666666666667

```


