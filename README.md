# AutoBuild-Lean'sOpenwrt

Action的.yml参考了esir的，进行了个人需求的修改。

esir's github : https://github.com/esirplayground/AutoBuild-OpenWrt


另外参考liuqi_colin@msn.com的两个修复自定义overlay挂载问题的patch，实现Actions上编译出可成功挂载自定义overlay的固件包。

liuqi's patch about fstools :

https://patchwork.ozlabs.org/project/openwrt/patch/BYAPR03MB444052C4846ECA6DB88B098D955E0@BYAPR03MB4440.namprd03.prod.outlook.com/
https://patchwork.ozlabs.org/project/openwrt/patch/BYAPR03MB4440353BF13FCB2C80389186955E0@BYAPR03MB4440.namprd03.prod.outlook.com/


在自己本地可以在make menuconfig 配置后

分别执行 make package/system/fstools/download 和 make package/system/fstools/prepare

然后按照patch内容直接修改package/system/fstools和build_dir/target-x86_64_musl/fstools-2020-07-11-53453438目录下的对应文件。

由于fstools这两处的patch均无历史patch，所以可以按照patch内容直接修改对应文件。

获取到修改后的文件，上传到github，就可以通过Actions过程中替换文件，实现编译出可成功挂载自定义overlay的固件包。
