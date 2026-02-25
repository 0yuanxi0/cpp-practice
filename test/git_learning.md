# 1. Git 核心操作“三板斧”

在 VS Code 终端中与我们的 [cpp-practice 远程仓库](https://github.com/0yuanxi0/cpp-practice.git) 交互时，必须严谨地执行以下步骤：

## 1.1 初始化与身份登记

Git 系统拒绝任何匿名提交。首次使用前，*必须*在终端执行身份核对：

```bash
git config --global user.name "yx"
git config --global user.email "真实邮箱（最好是github使用的邮箱）"
```

## 1.2 标准提交流程

为了便于记忆，可以把git上传的代码文件看作是一批货物，需要经过“打包->入库->发车”这三个严格的步骤

1. **打包（暂存）：** `git add .`
2. **入库（提交）：** `git commit -m "my first commit"`
3. **发车（推送）：** `git push -u origin main`

## 1.3 异常排错记录：网络连接重置

如果在推送时遇到 `Recv failure: Connection was reset` 错误，通常是因为终端未能识别本机的网络代理通道。

**解决方案：**

1.  清理可能残留的错误配置：

    ```bash
    git config --global --unset http.proxy
    git config --global --unset https.proxy
    ```

2.  强制为 Git 指定本地代理端口（一般默认本地端口为 7890）：

    ```bash
    git config --global http.proxy http://127.0.0.1:7890
    git config --global https.proxy http://127.0.0.1:7890
    ```
