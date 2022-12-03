Make a small change in [openssl.cnf](file:///C:/"Program Files"/Git/mingw64/ssl/openssl.cnf) file before running below command : Append following snippet to it :

[SAN]
subjectAltName=DNS:local.dev



```console
$ ./bin/openssl req -newkey rsa:2048 -x509 -nodes -keyout local_dev.key -new -out local_dev.crt -subj /CN=local.dev -reqexts SAN -extensions SAN -config ./ssl/openssl.cnf -sha256 -days 3650
```
