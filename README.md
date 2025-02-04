# 剑灵欧服汉化 - Blade & Soul Eu Client Localization in CN

## 作者
- [Monsterlady](https://monsterlady.cloud/)

## 特别感谢
特别感谢Discord中这位剑灵老玩家的提供的帮助, 他的ID是`Sanzerithy`，没有他的话是不可能完成欧服剑灵的汉化的。
<br/>
其次是`BnsMultiTool`的作者`Tonnilson`和`BnDatTool`的作者`ashllay`

## 说明
本项目是剑灵欧服汉化项目，目前基本已经完成了所有汉化工作，仍然有很小一部分内容(例如欧服特有的事件与活动)没有汉化，欢迎大家一起参与到汉化工作中来。

## 使用方法
1. 下载`Github`上的`Release`中的[汉化包](https://github.com/monsterlady/blade_and_soul_CN_localization/releases)
2. 解压缩到任意目录下
3. 打开剑灵游戏目录下的`X:\Blade & Soul_US\BNSR\Content\local\NCWest\English\data`文件夹, 将原本的`local64.dat`改名为`local64-origin.dat`, 然后将汉化包中的`local64.dat`文件复制到此目录下
   
~~4. 打开`X:\BNS_EU\Blade & Soul_US\BNSR\Content\Paks`,  将汉化包中的`Mods`文件夹复制到此目录下~~
~~5. 打开`X:\BNS_EU\Blade & Soul_US\BNSR\Binaries\Win64`, 将汉化包中的`winmm.dll`文件复制到此目录下~~
~~6. 然后再将将汉化包中的`plugins`文件夹复制到此目录下~~

7. 打开游戏即可看到汉化效果
8. 如果想要卸载汉化包, 只需要删除`local64.dat` 将`local64-origin.dat`文件改回原名, 将`Mods`文件夹,`plugins`文件夹和`winmm.dll`文件删除即可

## 汉化进度
- [x] 剧情对话
- [x] 界面
- [x] 物品
- [x] 技能
- [x] 成就
- [x] 任务
- [x] 副本
- [x] 世界地图
- [x] 人物
- [x] 商店
- [x] 仓库
- [x] 任务

## 汉化方法
1. 本汉化项目使用了解包`BnsMultiTool`工具后的部分dll注入式文件作为基座。
2. 使用了`BndDatTool`工具来解包和合并`local64.dat`文件
3. 使用了以`DatV3_xmlV4`为密钥进行解包和合并
4. 使用了`bnstool-public-2021-11-04_beta4`工具中的部分文件, 为剑灵UE3时代的老工具, 不能保证其稳定性和安全性
