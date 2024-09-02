# acme.sh excercise

## Install 

```sh
curl https://get.acme.sh | sh -s email=my@example.com
```

## Prepare DNS API Keys

```sh
export CF_Token=REPLACE_ME
export CF_Zone_ID=REPLACE_ME
export CF_Account_ID=REPLACE_ME
```

## Issue cert (Test)

[server list](https://github.com/acmesh-official/acme.sh/wiki/Server)

```sh
acme.sh --issue --dns dns_cf --server letsencrypt_test -d <your-subdomain>.softsquaregroup.app 
```

i.e.: 

```sh
acme.sh --issue --dns dns_cf --server letsencrypt_test  -d my-172-16-250-63.softsquaregroup.app --log

# wildcard
acme.sh --issue --dns dns_cf --server letsencrypt_test  -d '192-168-56-2.softsquaregroup.app' -d '*.192-168-56-2.softsquaregroup.app' --log
```

# Ready for production Cert?

```sh
acme.sh --renew --force --dns dns_cf --server letsencrypt  -d my-172-16-250-63.softsquaregroup.app --log
```

[more](https://github.com/acmesh-official/acme.sh)