<h1 align="center">吴语·温州话<a rel="繁体中文" href="/README.md"><br><font size="4">繁体中文</font></a><br>

[![LICENSE](https://img.shields.io/badge/license-AGPL3.0-blue?style=for-the-badge)](https://github.com/ZWolken/rime-wenzhounese/blob/main/LICENSE)<br>
[![GitHub Repo stars](https://img.shields.io/github/stars/ZWolken/rime-wenzhounese?style=for-the-badge)](https://github.com/ZWolken/rime-wenzhounese)
[![GitHub all releases](https://img.shields.io/github/downloads/ZWolken/rime-wenzhounese/total?style=for-the-badge)](https://github.com/ZWolken/rime-wenzhounese/releases)

# [Rime](https://rime.im) 吴语-温州话输入方案

字典根据沈克成-沈迦的拼音方案进行录入。

模糊音方案规则主要模糊了浊音的辅音叠写，若有需要可导入模糊音文件以开启。

拼写方案及字词典来源：
1.	温州话/沈克成,沈迦著.—宁波:宁波出版社,2004.11
	- ISBN 7-80602-811-0
2.	温州话:增补本/沈克成,沈迦著.—宁波:宁波出版社,2013.3
	- ISBN 978-7-5526-0708-6
> 注意：部分内容使用了OCR以及简繁转换工具，校对后仍可能会有错误存在，若发现错误敬请提交Issue说明。

参考资料：
1.	[汉典](https://www.zdic.net/)
2.	[小學堂|漢字古今字資料庫](https://xiaoxue.iis.sinica.edu.tw/ccdb)
3.	[拼字输入法](https://hanzi.unihan.com.cn/PinZi)
4.	[两分查字](http://zisea.com/zslf.htm)
5.	[中文简繁体转换](https://tool.lu/zhconvert/)
6.	[正则表达式测试](https://regexr-cn.com/)
7.	[汉字字符集编码查询](https://www.qqxiuzi.cn/bianma/zifuji.php)
8.	[異体字リスト](https://www.tobunken.go.jp/archives/%E7%95%B0%E4%BD%93%E5%AD%97%E3%83%AA%E3%82%B9%E3%83%88/)
9.	[Schema.yaml 詳解](https://github.com/LEOYoon-Tsaw/Rime_collections/blob/master/Rime_description.md)
10.	[鼠须管配置使用](https://blog.isteed.cc/post/squirrel-customization-2022/)

## 安装

1.	根据系统下载安装对应的[Rime输入法引擎](https://rime.im/download/)版本

-	Android系统安装使用可参阅[osfans/trime](https://github.com/osfans/trime)以及[SivanLaai/rime-pure](https://github.com/SivanLaai/rime-pure)
-	iOS系统安装使用可参阅[Hamster](https://github.com/imfuxiao/Hamster)

2.	从[Release（发行版发布页）](https://github.com/ZWolken/rime-wenzhounese/releases/latest)下载最新版本的数据文件。
-	压缩包文件或者全部的`*.yaml`结尾的文件选一者全部下载即可。
-	压缩包下载完成后请解压到可自行可操作的文件夹备用。
-	<details>
	<summary>不会解压缩文件？</summary>
	请查阅<a href="https://[www.runoob.com/](https://blog.csdn.net/weixin_44168217/article/details/96311980)">压缩包解压教程</a>。
	</details>

3.	将系统输入切换至Rime输入法

4.	在状态栏上右键Rime图标，点击`用戶文件夾`以开启
-	<details>
	<summary>亦可手动打开Rime用户文件夹，路径如下：</summary>
	【中州韻】<code>~/.config/ibus/rime/</code><br>
	【小狼毫】<code>%APPDATA%\Rime</code><br>
	【鼠鬚管】<code>~/Library/Rime/</code>
	</details>

5.	将以`*.yaml`结尾的文件均复制至`用戶資料夾`内

	-	`wenzhounese.custom.yaml`文件是针对原拼写方案的模糊音定制方案文件，使用后一定程度上可根据普通话拼音的逻辑进行输入
	-	对于模糊音定制方案文件可见[模糊音方案说明](/FuzzySoundList.md)
	-	注意：模糊音定制方案文件导入使用后将升高重码率，如果要只使用原拼写方案进行输入的话不导入此文件即可

6.	在状态栏上右键Rime图标，点击`輸入法設定`以打开启设定界面，勾选中`溫州話輸入法`以开启

7.	在状态栏上右键Rime图标，点击`重新部署`

8.	按下<kbd>Ctrl</kbd>+<kbd>｀</kbd> 或 <kbd>F4</kbd>（Rime默认快捷键），唤出方案选单，选择`溫州話輸入法`

9.	开始输入

## 简繁体字形转换

### 默认繁体字形原因

考虑到繁体字形保留的信息比简体字形要多，且繁转简比简转繁要**容易且不容易出错**很多，因此字词库在录入时均使用繁体字形。

### 如何输出简体字形

Rime输入法引擎自带繁简转换功能，具体步骤如下：
1.	切换至Rime输入法

2.	按下<kbd>Ctrl</kbd>+<kbd>｀</kbd> 或 <kbd>F4</kbd>（Rime默认快捷键），唤出方案选单，选择`溫州話輸入法`

3.	再次按下<kbd>Ctrl</kbd>+<kbd>｀</kbd> 或 <kbd>F4</kbd>，重新唤出方案选单

4.	再次选择`溫州話輸入法`，此时会进入下一级菜单

5.	选择`3. 漢字 → 汉字`，此时该选项会变为`3. 汉字 → 漢字`，即可开启简体字形输出
> 若需切换回繁体字形，重复上述步骤改回`3. 漢字 → 汉字`的状态即可<br>
> 注意：此简体字形输出更改行为为临时更改，在切换输入法后会重新回到繁体字形输出模式。

### 如何将简体字形输出设置为默认

1.	在状态栏上右键Rime图标点击`用戶文件夾`以开启
-	<details>
	<summary>亦可手动打开Rime用户文件夹，路径如下：</summary>
	【中州韻】<code>~/.config/ibus/rime/</code><br>
	【小狼毫】<code>%APPDATA%\Rime</code><br>
	【鼠鬚管】<code>~/Library/Rime/</code>
	</details>

2.	使用`记事本`或`Visual Studio Code`等软件打开`wenzhounese.schema.yaml`文件

3.	跳转到第23行，具体代码应如下：
```yaml
22  - name: simplification
23    #reset: 1   # 0[默認缺省值]：輸出原字形（繁體）；1：啓用「繁→簡」轉換，輸出簡體字
24    states: [ 漢字, 汉字 ]
```

4.	删除第23行行首的`#`符号，修改成如下所示：
```yaml
reset: 1   # 0[默認缺省值]：輸出原字形（繁體）；1：啓用「繁→簡」轉換，輸出簡體字
```

5.	保存文件更改

6.	在状态栏上右键Rime图标，点击`重新部署`

7.	唤出方案选单，再次选择`溫州話輸入法`

8.	此时已将简体字形输出设置为默认状态
> 若需切换回默认繁体字形输出，将即可`wenzhounese.schema.yaml`的第23行行首的`#`符号添加回即可。

## 任务清单 To-Do List

- [x] 基础字汇录入（2004年版本）
- [ ] 基础字汇更新（拼写方案更新至2013年版本）
- [ ] 拓展字汇录入（更新至《温州话字林》的2w+字头）
- [x] 基础词汇录入（2013年版本）
- [ ] 拓展词汇录入（更新至《温州话辞典》的全部词汇）
- [x] 模糊音规则编写（基于2004年版本）
- [ ] 模糊音规则更新（基于2013年版本）
- [ ] 输入方案打包成输入法安装包

**录入量巨大**，**目前完成时间未知**，若有想帮忙者可通过[zwolken@foxmail.com](mailto:zwolken@foxmail.com)邮箱地址找到我进行后续联系。感激不尽！

## 许可 & 许可证

- [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.html)

```
Copyright (C) 2023 Wolken(zwolken@foxmail.com | zharry@web.de)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
```

本项目已获得沈克成先生的授权，可使用沈克成先生所出版书籍的内容。<br>
版权所有 © 2023 Wolken (zwolken@foxmail.com | zharry@web.de)
