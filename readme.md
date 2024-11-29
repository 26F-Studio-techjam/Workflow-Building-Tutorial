# Techmino-Series 开发环境搭建教程

## Windows

1. 安装Git，这是用于联网同步工程文件夹的工具
1. 安装love2d，这是运行项目的游戏引擎
    1. 点击 [Love2d](https://www.love2d.org) 打开官网，根据自己电脑下载64位或者32位的安装包，用zipped压缩包就可以
    1. 确定love2d安装在哪了，把路径复制一下，之后要用
1. 安装VS Code (VSC)，这是编辑代码的工具  【记事本也行，但相信我，别这么干】
    1. 点击 [VS Code](https://code.visualstudio.com) 打开官网并安装
    1. 下载游戏项目
        1. 去项目仓库首页点开那个很显眼的“Code”绿色按钮，点开有个小弹窗里面有一行地址，复制它
        1. VSC会自动识别到安装了Git然后打配合，打开VSC的命令面板找到命令 `Git: Clone` 执行，然后选择一个文件夹作为项目文件夹的下载位置，就下载好了（下完了后应该会让你立刻打开）
    1. 安装 `Love2D executor` 插件，用于启动项目  【不然你就得手动在命令行里执行 `/path/to/love/love.exe /path/to/project` 了】
        1. 打开VSC的设置，搜索love2d，应该可以搜到这个插件的设置，有一个路径path配置，填入安装love2d后你记录的路径
        1. 之后你就可以在命令面板里找到一个叫 `love2d-executor.run` 的命令，选它就会把当前VSC打开的“工作文件夹”路径丢给你安装的love2d.exe执行，也就是运行当前项目
        1. 你还可以给上面这条VSC命令配置一个快捷键比如 Alt+L，一键启动更方便
    1. 安装 `Lua (sumneko)`插件，用于代码高亮和自动补全  【不然你就得纯手工敲代码了】
        1. 去命令面板中搜索到 `Lua: Open Addon Manager` 命令并执行，在打开的页面中搜索LÖVE并安装（就一个）

## Linux

我相信你不需要我教，以下是关键词：  
git, submodule  
love2d

## macOS

不熟，你加油

## Android

你是超人，我也不会，你加油
