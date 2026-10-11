> 最后更新：2026-10-12

# 剑灵欧服汉化 - Blade & Soul EU Client Localization in CN

## 作者
- [Monsterlady](https://monsterlady.io/)

## 特别感谢
特别感谢Discord中这位剑灵老玩家的提供的帮助, 他的ID是`Sanzerithy`，没有他的话是不可能完成欧服剑灵的汉化的。
<br/>
其次是`BnsMultiTool`的作者`Tonnilson`、`BnDatTool`的作者`ashllay`，以及`BnSTranslate`的作者。

## 说明
本项目是剑灵欧服汉化项目，文本来自**台服官方繁体中文**，按文本的 code 一一对应搬运到欧服客户端，对不上的部分（例如欧服特有的事件与活动）保持英文。欢迎大家一起参与到汉化工作中来。

> ⚠️ **新版只需要替换一个 `local64.dat` 文件**，不再需要 `Mods`、`plugins`、`winmm.dll`。

适用客户端版本：`5.41.10646.18`（可在 `X:\Blade & Soul_US\BNSR\Binaries\Win64\version.ini` 中查看）。游戏更新后旧的汉化包可能失效（文字显示为 `#INVALID#`），请等待新版本的 Release。

## 使用方法
1. 下载`Github`上的`Release`中的[汉化包](https://github.com/monsterlady/blade_and_soul_CN_localization/releases)
2. 打开剑灵游戏目录下的`X:\Blade & Soul_US\BNSR\Content\local\NCWest\English\data`文件夹, 将原本的`local64.dat`改名为`local64-origin.dat`, 然后将汉化包中的`local64.dat`文件复制到此目录下
3. 打开游戏即可看到汉化效果

如果想要卸载汉化包, 只需要删除`local64.dat`, 将`local64-origin.dat`文件改回原名即可。

**旧版用户**：请先删除之前安装的`Paks\Mods`文件夹、`Binaries\Win64\plugins`文件夹和`Binaries\Win64\winmm.dll`，否则游戏可能无法启动。

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
- [ ] 过场动画字幕
- [ ] 欧服特有的事件与活动

## 已知问题
- 欧服字体只包含部分中文字，少量生僻字会显示为菱形问号。中文标点已统一替换为英文标点以减少问号。
- 少量文本结尾缺字，部分道具名、NPC 名可能显示不全。
- 文本来自台服，个别技能、装备描述里的数值可能与欧服实际不同，以游戏内实际效果为准。

## 汉化方法
### 新版
1. 使用自制脚本解包台服与欧服的`local64.dat`，按文本 code 将台服繁体中文合并进欧服文本，并将中文标点转换为英文标点
2. 使用 [BnSTranslate](https://www.bnsbuddy.com/threads/bnstranslate-%E2%80%94-all-in-one-translation-tool.5208/) 以欧服官方`local64.dat`为目标重新打包

### 旧版（已停用）
1. 本汉化项目使用了解包`BnsMultiTool`工具后的部分dll注入式文件作为基座。
2. 使用了`BndDatTool`工具来解包和合并`local64.dat`文件
3. 使用了以`DatV3_xmlV4`为密钥进行解包和合并
4. 使用了`bnstool-public-2021-11-04_beta4`工具中的部分文件, 为剑灵UE3时代的老工具, 不能保证其稳定性和安全性

## 免责声明
本项目仅供学习交流，与 NCSOFT 无关。修改客户端文件违反剑灵用户协议，存在账号被处罚的风险，请自行权衡。
