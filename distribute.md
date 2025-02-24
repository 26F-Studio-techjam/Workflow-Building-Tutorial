# Love2d项目的发布

对于love2d项目，你并不能神奇地“编译项目”变成一个包，而是直接把工程文件夹里的东西打成zip压缩包

这种love2d工程压缩包可以被love直接运行，所以我们通常都会把这个压缩包重命名成`游戏名.love`

这样会方便在windows或者linux中设置.love文件的默认打开方式为love2d引擎，就能双击运行了

这个压缩包推荐使用仅存储的zip格式，不然可能会导致加载变慢（具体慢多少自己试试，可能随项目而异）

## Windows

在love.exe的文件夹内，运行

`copy /b love.exe+工程.love 游戏名.exe`

以此合并love引擎和游戏工程，生成的新文件相当于之前命令里让love引擎运行工程

接下来你就可以把这个exe文件和其他资源文件（不包括原本的love.exe）打包成一个压缩包发布了

## Linux（AppImage）

下载官方的AppImage，然后运行

`love.appimage --appimage-extract`

你会得到一个`squashfs-root`文件夹，里面的结构类似于linux的系统根目录，你需要知道的有：

`usr/bin/love` 这是love引擎的可执行文件，相当于love.exe

`share/pixmaps/` `share/mime/` `share/icon/` `share/applications/`  
这些共享资源文件夹里的东西我全删了，好像不影响

`love.desktop` 这是决定桌面环境相关的元信息文件

- 这个文件名无所谓，要改的基本只有Name和Comment
- Icon直接写一个icon然后在根目录放一个icon.png就行，如果保留love的话可能会自动引用到上一步里你没删掉的图标之类的，反正我是删了（包括原本根目录的love.svg）
- Exec这段不需要，我留空了

`AppRun` 这是启动脚本，运行.appimage时会执行它

然后有两种方式引入项目文件：

1. 你可以把.love工程和`usr/bin/love`用cat命令连接成一个新的可执行文件然后覆盖掉原本的，AppRun脚本中默认就会去运行love，就不用做别的了

1. 我更喜欢直接把工程文件夹（.love也行）拿过来，我猜不弄成压缩文件会让性能好些？  
比如有一个叫mygame的文件夹在根目录，那么AppRun中的启动命令改成如下的版本即可：

`exec "$APPDIR/bin/love" --fused "$APPDIR/mygame" "$@"`
