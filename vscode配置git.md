# vscode中如何配置git和gitee

## 1.配置个人信息
安装git管理工具后
```bash
# 配置个人信息
git config --global user.name "cnsonkwl"
git config --global user.email "sonkwl@163.com"
```
## 2.初始化本地库
进入vscode
- 资源管理器中新建或载入文件夹
- vscode->源代码管理，初始化代码库
    ```bash
    # 多个代码库，需手动初始化
    cd dir
    git init
    ```
- 进入目录的终端,设置远程库地址
    ```bash
    git remote add origin https://gitee.com/cnsonkwl/my.git
    git push -u origin master
    ```

## 3.GIT使用代理

```bash
git config --global http.proxy=http://
git config --global https.proxy=http://
```
    
---
# 旧版配置
## 1.配置git
### 1.1 安装git软件(略)
### 1.2 生成ssh公钥

```bash
# 生成密钥
ssh-keygen -t rsa -C "sonkwl@163.com"
# 查看密钥
cat ~/.ssh/id_rsa.push
#ssh-rsa AAAA....
```

### 1.3 gitee中配置公钥

gitee仓库中，新增公钥

### 1.4 ssh配置(只使用https可不用配置)

```bash
ssh -T git@gitee.com
```

### 1.5 git初始化

```bash
# 配置个人信息
git config --global user.name "cnsonkwl"
git config --global user.email "sonkwl@163.com"

# 初始化本地库
# e:/mynode 为新增本地库
e:/mynode/~ git init
```
目录下多了一个.git的目录

### 1.6 关联gitee仓库

```bash
git remote add origin https://gitee.com/cnsonkwl/mynode.git
#或(需配置1.4)
git remote add origin git@gitee.com:cnsonkwl/mynode.git
```
---

## 2 git常用操作(使用vscode，可略过)
### 2.1 拉取代码
```bash
git pull origin master --allow-unrelated-histories
# --allow-unrelated-histories 
# 解决git2.9版本之后报错refusing to merge unrelated histories
```

### 2.2 提交代码
```bash
# 新增文件
git add test.md
git commit -m "msg"
```

### 2.3 上传远程库
```bash
git push origin master
```
---

## 3 vscode操作
[网站链接](https://blog.csdn.net/weixin_46571373/article/details/107525877)


