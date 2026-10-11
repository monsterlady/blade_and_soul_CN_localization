# 剑灵欧服汉化 - Blade & Soul EU Client Localization in CN

## 作者
- [Monsterlady](https://monsterlady.io/)

## 特别感谢
特别感谢Discord中这位剑灵老玩家的提供的帮助, 他的ID是`Sanzerithy`，没有他的话是不可能完成欧服剑灵的汉化的。
<br/>
其次是`BnsMultiTool`的作者`Tonnilson`、`BnDatTool`的作者`ashllay`，以及新版重新打包所用的`BnSTranslate`的作者。

## 说明
本项目是剑灵欧服汉化项目，文本来自**台服官方繁体中文**，按文本的 code（alias）一一对应搬运到欧服客户端：
- code 对得上的文本 → 替换为台服中文
- code 对不上的文本（例如欧服特有的事件、活动、商城道具） → 保持英文

目前约 **134 万 / 160 万条**文本已汉化，剩余约 26 万条主要是欧服独有内容。欢迎大家一起参与到汉化工作中来。

> ⚠️ **新版（2026.10 起）只需要替换一个 `local64.dat` 文件**，不再需要 `Mods`、`plugins`、`winmm.dll`。

## 适用版本
| 汉化包版本 | 对应欧服客户端版本 |
|---|---|
| 最新 Release | `5.41.10646.18` |

客户端版本可以在 `X:\Blade & Soul_US\BNSR\Binaries\Win64\version.ini` 中查看。
**游戏每次更新后，旧的汉化包可能无法使用（文字显示为 `#INVALID#`），请等待对应新版本的 Release。**

## 使用方法
1. 下载`Github`上的`Release`中的[汉化包](https://github.com/monsterlady/blade_and_soul_CN_localization/releases)（只有一个 `local64.dat`）
2. 打开剑灵游戏目录下的`X:\Blade & Soul_US\BNSR\Content\local\NCWest\English\data`文件夹
3. 将原本的`local64.dat`改名为`local64-origin.dat`作为备份
4. 将汉化包中的`local64.dat`复制到此目录下
5. 打开游戏即可看到汉化效果

### 卸载
删除`local64.dat`，将`local64-origin.dat`改回`local64.dat`即可。
也可以直接在启动器里使用「修复/校验文件」功能恢复官方文件。

### 旧版用户请注意
如果之前安装过旧版汉化包，请先删除以下文件，否则游戏可能报错或无法启动：
- `X:\Blade & Soul_US\BNSR\Content\Paks\Mods` 文件夹
- `X:\Blade & Soul_US\BNSR\Binaries\Win64\plugins` 文件夹
- `X:\Blade & Soul_US\BNSR\Binaries\Win64\winmm.dll`

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
- [ ] 过场动画字幕（`textdata.subtitle.x16`，仍为英文）
- [ ] 欧服独有的活动、商城道具（台服没有对应文本，保持英文）

## 已知问题
- **部分字符显示为菱形问号（◆?）**：欧服客户端自带的字体只包含部分中文字。新版已将中文标点（，。「」【】…）全部替换为英文标点，大部分问号已消失；少量生僻字（如「闇」「鎧」「喵」）仍可能无法显示。
- **使用繁体而不是简体**：测试发现欧服字体对繁体的覆盖比简体好，转换成简体后问号反而更多。
- **少量文本结尾缺字**：重新打包时约 1.9 万条文本（约 1.2%）结尾被截掉 1~15 个字，部分道具名、NPC 名的引用可能显示不全，已反馈给打包工具作者。
- **数值可能与欧服不一致**：文本来自台服，台服和欧服的平衡调整不完全同步，个别技能、装备描述中的数值可能与欧服实际不符，以游戏内实际效果为准。
- **名称为台服译名**：人名、地名、道具名都是台服的繁体译名，与国服简体译名不同。

## 汉化方法
### 新版（2026.10 起）
1. 解包台服与欧服的`local64.dat`（AES 加密 + zlib 压缩的 `UOSEDALB` v3 格式），读取其中`localfile64.bin`的文本表
2. 按文本的 alias 将台服中文合并进欧服文本表：
   - 台服文本为空或为`#no text`时保留英文，避免把欧服原有内容替换成空白
   - 中文全角标点转换为英文半角标点（不会转成`< > &`，以免破坏游戏的格式标签）
3. 使用 [BnSTranslate](https://www.bnsbuddy.com/threads/bnstranslate-%E2%80%94-all-in-one-translation-tool.5208/) 以欧服官方`local64.dat`为 Target 重新打包，生成游戏可以加载的文件

合并工具为 Python 脚本（`bnsdat.py` / `localbin.py` / `merge.py`），游戏更新后可重新生成：
```
python merge.py --eu "<欧服官方 local64.dat 路径>" --tw "<台服 local64.dat 路径>"
```
生成的文件在`output\local64.dat`，再用 BnSTranslate 打包即可。

### 旧版（已停用）
<details>
<summary>点击展开</summary>

1. 本汉化项目使用了解包`BnsMultiTool`工具后的部分dll注入式文件作为基座。
2. 使用了`BndDatTool`工具来解包和合并`local64.dat`文件
3. 使用了以`DatV3_xmlV4`为密钥进行解包和合并
4. 使用了`bnstool-public-2021-11-04_beta4`工具中的部分文件, 为剑灵UE3时代的老工具, 不能保证其稳定性和安全性

旧版安装步骤（已停用，仅作记录）：
- ~~打开`X:\BNS_EU\Blade & Soul_US\BNSR\Content\Paks`, 将汉化包中的`Mods`文件夹复制到此目录下~~
- ~~打开`X:\BNS_EU\Blade & Soul_US\BNSR\Binaries\Win64`, 将汉化包中的`winmm.dll`文件复制到此目录下~~
- ~~然后再将汉化包中的`plugins`文件夹复制到此目录下~~
</details>

## 免责声明
本项目仅供学习交流，与 NCSOFT 无关。修改客户端文件违反剑灵用户协议，存在账号被处罚的风险，使用前请自行权衡，作者不对由此产生的任何后果负责。
