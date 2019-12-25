# openwrt-r619ac-build
## P&W R619AC/竞斗云/G-Dock 2.0 OpenWrt/LEDE编译配置文件&预编译固件（自用&备份用）

插件列表请参考Releases中的config.seed。适配R619AC 128M，请使用合适的方式刷入。
如使用编译好的版本，建议自行核对sha256。

编译时遇到的一点点坑：
我使用的是Arch Linux，由于软件包版本比较新，出现了编译报错的情况，类似此帖：https://forum.openwrt.org/t/build-problem-18-06-4-libgpg-error/45910
新版移除了某些头文件导致了编译失败。

解决方案：降级gawk至4.2.1，make clean后重新编译
```
$ yay -S downgrade	#安装downgrade脚本方便降级，可添加archlinuxcn源或从AUR安装
$ downgrade gawk
可选的包：

   1)  gawk    4.2.1  2  x86_64  (远端)
   2)  gawk    4.2.1  2  x86_64  (本地)
   3)  gawk    5.0.1  1  x86_64  (远端)
+  4)  gawk    5.0.1  2  x86_64  (远端)
+  5)  gawk    5.0.1  2  x86_64  (本地)

输入数字以选择包： 2
```
即可。
