
# Issue Description

get below error when cloning data from github or pushing to Git hub
```
Cloning into 'MoBA'...
ssh: connect to host github.com port 22: Connection timed out
fatal: Could not read from remote repository.

```

tried to ping github.com, failed:
```
C:\Users\Harry>ping github.com

正在 Ping github.com [20.205.243.166] 具有 32 字节的数据:
请求超时。

20.205.243.166 的 Ping 统计信息:
    数据包: 已发送 = 1，已接收 = 0，丢失 = 1 (100% 丢失)，
```

# Solution

## Using SSH Over the HTTPS port
References:
- [解决 SSH 连接 GitHub 出现 Connection Closed](https://paugram.com/tech/github-ssh-connection-closed-problem-with-proxy.html)
- [Github - Using SSH Over the HTTPS port](https://docs.github.com/en/authentication/troubleshooting-ssh/using-ssh-over-the-https-port)

Step 1: Test port 443 connection
```
$ ssh -T -p 443 git@ssh.github.com
Hi xxx! You've successfully authenticated, but GitHub does not provide shell access.

```

Step 2: edit or create the file in ~/.ssh/config or windows: C:\Users\{Your User name}.ssh
```
Host github.com
    Hostname ssh.github.com
    Port 443
    User git
```

Step 3: Test the connection
```
$  ssh -T git@github.com
Hi xxx! You've successfully authenticated, but GitHub does not provide shell access.

```

then it works
