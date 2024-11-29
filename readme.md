# Techmino-Series 开发环境搭建教程

## Windows

1. 安装Git，这是用于联网同步工程文件夹的工具
1. 安装love2d，这是运行项目的游戏引擎
    1. 点击 [Love2d](https://www.love2d.org) 打开官网，根据自己电脑下载64位或者32位的安装包，用zipped压缩包就可以
    1. 确定love2d安装在哪了，把路径复制一下，之后要用
1. 安装VS Code (VSC)，这是编辑代码的工具  【记事本也行，但相信我，别这么干】
    1. 点击 [VS Code](https://code.visualstudio.com) 打开官网并安装
    1. 在VSC中配置Git
        1. VSC其实会自动识别到安装了Git然后打配合
        1. 由于后续的一些操作会涉及到身份验证，比如一些仓库并不对所有人公开，你需要向VSC证明你是某个GitHub账号的持有者，所以你需要在VSC中登录你的GitHub账号
            1. VSC左下角有个账号图标，点它然后按照指示登录，之后在VSC内进行的一些GitHub操作就可以顺利执行
        1. 【超纲】如果你需要修改代码并提交，那么你还需要配置一下Git的用户名和邮箱，给你所修改来签名
            1. 打开命令行（当前位置无所谓），执行 `git config --global user.name MrZ` 命令，记得把MrZ换成你的名字（那个普通的用户名即可，*不必*是那个唯一的用户ID）
            1. 【补充】其实这两个命令就是在修改用户文件夹（C:\Users\用户名）里的 `.gitconfig` 文件，可以去找出来看看里面写了什么，也可以拖进VSC窗口里手动编辑这个文件来进行配置，你可以试试用这个办法来跳过下一步
            1. 再执行 `git config --global user.email` 命令，记得换成你自己的邮箱（***重要***，应当是你在GitHub登记的邮箱）
    1. 下载游戏项目
        1. 去项目仓库首页点开那个很显眼的“Code”绿色按钮，点开有个小弹窗里面有一行地址，复制它
        1. 打开VSC的命令面板找到命令 `Git: Clone` 执行，然后选择一个文件夹作为项目文件夹的下载位置，就下载好了（下完了后应该会让你立刻打开）
        1. 【超纲】对于包含子模块的仓库，你需要知道怎么初始化/更新子模块
            1. 打开命令行，cd到项目文件夹，然后执行 `git submodule update --init` 命令来下载子模块的代码
            1. 未来如需更新还要执行同样的命令`git submodule update`，另一个更有参与感的等价的方法是在控制台里cd进子模块文件夹然后执行 `git pull` （最后别忘了再 `cd ..` 出来）
    1. 安装Love2D执行插件用于启动项目  【不然你就得手动在命令行里执行 `/path/to/love/love.exe /path/to/project` 了】
        1. VSC插件市场找到 `Love2D executor` 插件并安装
        1. 打开VSC的设置，搜索love2d，应该可以搜到这个插件的设置，有一个路径path配置，填入安装love2d后你记录的路径
        1. 之后你就可以在命令面板里找到一个叫 `love2d-executor.run` 的命令，选它就会把当前VSC打开的“工作文件夹”路径丢给你安装的love2d.exe执行，也就是运行当前项目
        1. 你还可以给上面这条VSC命令配置一个快捷键比如 Alt+L，一键启动更方便
    1. 安装Lua语言服务插件，用于代码高亮和自动补全  【不然你就得纯手工敲代码了】
        1. VSC插件市场找到 `Lua (sumneko)` 插件并安装
        1. 去命令面板中搜索到 `Lua: Open Addon Manager` 命令并执行，在打开的页面中搜索LÖVE并安装（就一个）

## Linux

我相信你不需要我教，以下是关键词：
git, submodule
love2d

## macOS

不熟，你加油

## Android

你是超人，我也不会，你加油
