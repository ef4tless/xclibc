# xclibc
A tool to change the libc environment of running files
![image](https://user-images.githubusercontent.com/52035000/192832394-8af0bf43-1be1-4d5b-8701-9b0d8057b190.png)


## Usage
This script is based on the glibc-all-in-one project

I suggest you install it in `~/`
```
git clone https://github.com/matrix1001/glibc-all-in-one
cd glibc-all-in-one
./update_list
```
configuration
```
cd xclibc
sudo rm /usr/local/bin/xclibc
sudo mv ./xclibc /usr/local/bin
sudo chmod +x /usr/local/bin/xclibc
```
## Update
v0.5: 重定义了选项命令
v0.3: 添加了解压deb包的功能
## Warning
This script will delete /usr/lib/debug/.build/ before patching. If you mind, please backup it first
## Last
If you encounter any problems in using this script, please contact me as soon as possible
