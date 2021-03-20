# Bash Note

**List all envrionment variables**
```shell
$ env
```

**Get a variable**
```shell
$ echo $varname
```

**Set a variable**
```shell
$ export varname=value
```

**Unset http proxies (LOCAL)**
```shell
$ unset http_proxy
$ unset https_proxy
$ unset HTTP_PROXY
$ unset HTTPS_PROXY
```

```bash
#!/bin/bash
# <filename>.sh

echo "Removing HTTP/HTTPS Proxies";
unset http_proxy;
unset https_proxy;
unset HTTP_PROXY;
unset HTTPS_PROXY;

# Note: Executing file with ./<filename> will only unset the proxies on subshell
# Therefore, use source command to run this script eg. source <filename>.sh

```


## References
- [Environment Variables in Windows/macOS/Linux](https://www3.ntu.edu.sg/home/ehchua/programming/howto/Environment_Variables.html)
