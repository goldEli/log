# mienr 项目离线开发：

随着项目需求，有些局点需要去现场开发调试，且不能连接外网。本文主要介绍如何搭建 miner 项目的离线开发环境。（开发环境多为 windows，下文默认 windows 环境）

## 所需工具：

* nodejs 安装包
* vscode 安装包
* vscode 插件安装包
	* prettier
	* open in browser
	* ES7 React/Redux/GraphQL/React-Native snippets
	* Path Intellisense
* yarn 安装包
* yarn 缓存包（全局webpack等）
* python 安装包
* minerUI 源码包

## 准备


### python

下载 Python3

```
https://www.python.org/downloads/
```

### nodejs

下载长期维护版本

```
https://nodejs.org/zh-cn/
```
### vscode

下载最新版即可

```
https://code.visualstudio.com/
```

#### 下载安装 vscode 扩展插件

由于在 vscode 官网上找不到下载链接，需要拼接下载链接，以 prettier 为例：

原始 url 地址：

```
https://${publisher}.gallery.vsassets.io/_apis/public/gallery/publisher/${publisher}/extension/${extension name}/${version}/assetbyname/Microsoft.VisualStudio.Services.VSIXPackage
```
`${publisher}` `${extension name}` `${version}` 为变量。

打开 prettier 页面

```
https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode
```

根据上面的 url 地址，提取出 itemName 的值 esbenp.prettier-vscode

将原始地址中 `${publisher}` 替换成 `esbenp`，`${extension name}` 替换成 `prettier-vscode`，在网页中找到版本号为 1.6.1，将 `${version}` 替换。

最终得到 prettier 的下载地址为： 

```
https://esbenp.gallery.vsassets.io/_apis/public/gallery/publisher/esbenp/extension/prettier-vscode/1.6.0/assetbyname/Microsoft.VisualStudio.Services.VSIXPackage
```

下载后，将文件名 `Microsoft.VisualStudio.Services.VSIXPackage` 修改为 `prettier.vsix` 。

下载其他插件同理。

### yarn

```
https://yarnpkg.com/zh-Hans/
```

通过 yarn 命令安装项目相关依赖。

安装完成或，所有依赖会安装到缓存文件夹中。

```
yarn cache dir # 获取缓存文件地址
```

将缓存文件压缩，命名为 yarn_cache。

## 实施

依次安装 Python，nodejs， yarn， vscode。

### 安装 vscode 插件

以 prettier 为例：

打开 cmd，进入 prettier 所在的文件夹

```
code --install-extension prettier.vsix
```
出现

```
extension 'prettier.vsix' was successful installed!
```

即安装成功，重启 vscode 即可。

### yarn 缓存

在cmd中执行：

```
yarn cache dir # 获取缓存文件地址
```
将 yarn_cache 解压覆盖至该文件地址

### 启动项目

在 vscode 打开 mienrUI 源码包

执行：

```
yarn
```

此时 yarn 会从缓存路径中下载所有依赖。

# 完





