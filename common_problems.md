# Git 常见问题

### 1. 一台电脑配置`git`多用户，在`git clone`时，发生`Permission denied (publickey)`

```bash
git clone ...
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
```
> 解决步骤如下：（Windows）

1. 生成当前用户的key，将生成的公钥、私钥放置需要的地方
```bash
ssh-keygen -t rsa -C "***.com"
```
2. 将私钥添加ssh-agent中，首先安装ssh-agent服务,然后添加sshkey至ssh-agent
```bash
ssh-agent bash
ssh-add ~/.ssh/id_rsa
```
3. 将公钥至Github中的SSH中。