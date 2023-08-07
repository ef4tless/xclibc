# xclibc

![image](https://github.com/ef4tless/xclibc/assets/52035000/d7bdfe61-20f8-4474-a369-0ac7e5c99eef)


一个在CTF比赛中用于切换题目运行libc环境的工具，支持所有版本

## 安装

这个脚本是基于最新版的[glibc-all-in-one](https://github.com/matrix1001/glibc-all-in-one)，我建议你将其安装到`~`目录

```bash
git clone https://github.com/matrix1001/glibc-all-in-one
cd glibc-all-in-one
./update_list
```

xclibc脚本配置

```bash
git clone https://github.com/ef4tless/xclibc.git
cd xclibc
sudo rm /usr/local/bin/xclibc
sudo mv ./xclibc /usr/local/bin
sudo chmod +x /usr/local/bin/xclibc
```

本地libc库部署(*可选)
```bash
xclibc -d all
xclibc -d old
```

## 使用

```bash
xclibc [选项] [参数]
-s [libc文件] # 查看libc文件版本
-x [-n] [文件] [libc文件] # 一键给文件配置libc文件相应版本的环境（添加-n选项可以使用修改--replace-needed的方式实现）
-c [-n] [文件] [libc大版本号] [libc小版本环境路径] # 给文件配置指定的libc环境，输入大版本号后回车，可自由选择复制libc小版本环境路径（添加-n选项可以使用修改--replace-needed的方式实现）
-d <-r/-u> [version]/[all]/[old]
#  -d [ENTER] 可以查看所有可下载的libc版本
#  -d -r [version] 删除相应的libc版本库
#  -d -u 更新glibc-all-in-one libc版本列表(即清华源上有的libc版本列表)
#  -d all 下载所有源上有的libc版本
#  -d [version] 下载对应版本的libc
-e [deb包] # 解压相应的libc_deb包至glibc_all_in_one路径，通常一个版本需要解压一份本体deb和一份debug_deb包
-r [文件] # 恢复修改过的文件至初始状态
-h # 展示帮助提示
-v # 显示版本号
```

## 更新
v1.0: 增加了旧的下架版本的匹配，现在-x功能能匹配更多的版本了，完善了-d libc包管理功能，优化了部分逻辑处理方式

v0.9: 添加了-d下载libc版本库的功能，修复了2.31-0ubuntu9.10_amd64/i386不能加载的问题

v0.7：修复了一个bug，该bug曾导致2.31-0ubuntu9.9_amd64/i386 版本在加载后不能正常debug

v0.5: 重定义了选项命令

v0.3: 添加了解压deb包的功能

## 警告

这个脚本在patch过程中将会删除`/usr/lib/debug/.build/`，如果你介意这一点，请先备份本机文件。

## 最后

如果你在使用脚本中遇到任何的问题，请尽快联系我。

感谢cnitlrt师傅最初的脚本思路。
