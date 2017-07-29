# 文档

## nvm安装

### 下载 nvm 包

[nvm安装包下载链接](https://github.com/coreybutler/nvm-windows/releases)

我们选择第一个：nvm-noinstall.zip 下载完成后解压到一个地方，比如: D:\dev\nvm 里面的文件列表是这样的：elevate.cmd、elevate.vbs、install.cmd、LICENSE、nvm.exe

备注：windows下要设置显示文件类型的扩展名，这样才能看到上述文件的后缀

双击 install.cmd 然后会让你输入”压缩文件解压或拷贝到的一个绝对路径” 先不用管它，直接回车，成功后，会在C盘的根目录生成一个settings.txt的文本文件，把这个文件剪切到D:\dev\nvm目录中，然后我们把它的内容修改成这样：

```text
root: D:\dev\nvm
path: D:\dev\nodejs
arch: 64
proxy: none
node_mirror: http://npm.taobao.org/mirrors/node/
npm_mirror: https://npm.taobao.org/mirrors/npm/
```

然后我们开始配置环境变量了，因为刚刚点击了`install.cmd`的文件，那么会在环境变量的系统变量中，生成两个环境变量：`NVM_HOME` 和 `NVM_SYMLINK` 我们开始修改这两个变量名的变量值：`NVM_HOME`的变量值为：`D:\dev\nvm`； NVM_SYMLINK的变量值为：`D:\dev\nodejs`

我们还会发现，在Path中也会自动添加上`D:\dev\nvm`;或者是`D:\dev\nodejs`，如果有的话，把他们删掉，没有的话更好，我们自己来配置，在Path的最前面输入： `;%NVM_HOME%;%NVM_SYMLINK%;`

打开一个cmd窗口输入命令：`nvm v` ，那么我们会看到当前nvm的版本信息。然后我们可以安装nodejs了。

继续输入命令：`nvm install latest` 如果网络畅通，我们会看到正在下载的提示，下载完成后 会让你use那个最新的node版本。

如果你是第一次下载，在use之前，D:\dev目录下是没有nodejs这个文件夹的，在输入比如： nvm use 5.11.0 之后，你会发现，D:\dev目录下多了一个nodejs文件夹，这个文件夹不是单纯的文件夹，它是一个快捷方式，指向了 D:\dev\nvm 里的 v5.11.0 文件夹。

同样的咱们可以下载其他版本的nodejs，这样通过命令:`nvm use` 版本号 比如：nvm use 5.11.0就可以轻松实现版本切换了。

备注： 如果你的电脑系统是32 位的，那么在下载nodejs版本的时候，一定要指明 32 如：

`nvm install 5.11.0 32` 这样在32位的电脑系统中，才可以使用，默认是64位的。

## npm的安装

首先我们进入命令模式，输入 `npm config set prefix "D:\dev\nvm\npm"` 回车，输入 `npm config set cache "D:\dev\nvm\npm"` 回车，这是在配置npm的全局安装路径，然后在用户文件夹下会生成一个`.npmrc`的文件，用记事本打开后可以看到如下内容：

``` text
prefix=D:\dev\nvm\npm
cache=D:\dev\nvm\npm
```

然后继续在命令中输入： `npm install npm -g` 回车后会发现正在下载npm包，在D:\dev\nvm\npm目录中可以看到下载中的文件，以后我们只要用npm安装包的时候加上 -g 就可以把包安装在我们刚刚配置的全局路径下了。

我们为这个npm配置环境变量： 变量名为：`NPM_HOME`，变量值为 ：D:\dev\nvm\npm

在Path的最前面添加;`%NPM_HOME%`，注意了，这个一定要添加在 `%NVM_SYMLINK%`之前，所以我们直接把它放到Path的最前面

最后我们新打开一个命令窗口，输入npm -v ,此时我们使用的就是我们统一下载的npm包了。

同样的我们还可以安装cnpm工具，它是中国版的npm镜像库，[地址在这里](https://cnpmjs.org/)，也是npm官方的一个拷贝，因为我们和外界有一堵墙隔着，所以用这个国内的比较快，淘宝也弄了一个和npm一样的[镜像库](http://npm.taobao.org/)，它和官方的npm每隔10分钟同步一次。安装方式：

`npm install -g cnpm --registry=http://r.cnpmjs.org`

或者用淘宝的 `npm install -g cnpm --registry=https://registry.npm.taoba.org`
安装好了cnpm后，直接执行`cnpm install` 包名比如：`cnpm install bower -g` 就可以了。-g只是为了把包安装在全局路径下。如果不全局安装，也可以在当前目录中安装，不用-g就可以了。

## nrm 的安装

### 什么是nrm？

nrm就是npm registry manager 也就是npm的镜像源管理工具，有时候国外资源太慢，那么我们可以用这个来切换镜像源。
我们只要通过这个命令: `npm install -g nrm` 就可以实现安装。

注意-g可以直接放到install的后面，我们以后也最好这样用，因为这样用，我们可以在cmd中上下箭头切换最近命令的时候，容易修改，更方便操作。安装完成后，我们就可以使用了。

命令：`nrm ls` 用于展示所有可切换的镜像地址

命令：`nrm use cnpm` 我们这样就可以直接切换到cnpm上了。当然也可以按照上面罗列的其他内容进行切换。

## npm 常用命令

``` bash
# npm 帮助
npm help install
# 编辑全局设置
npm config edit -g
# 查看已全局安装过的包
npm list -g --depth=0
# 查看都安装了哪些全局包
npm outdated -g --depth=0
# 显示全局包安装路径
npm root -g
```
