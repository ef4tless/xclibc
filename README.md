# xclibc
A libc environment switching tool
![D22GVYJ06YUU6~$GZ50@5(Q](https://user-images.githubusercontent.com/52035000/192204442-58215a17-09ea-4a55-8df7-ef55671e04e9.png)
![image](https://user-images.githubusercontent.com/52035000/192210088-38295da1-d89f-46bc-9d75-3e86dcbae128.png)

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
sudo mv ./xclibc /usr/local/bin
sudo chmod +x /usr/local/bin/xclibc
```
## warning
This script will delete /usr/lib/debug/.build/ before patching. If you mind, please backup it first
## last
If you encounter any problems in using this script, please contact me as soon as possible
