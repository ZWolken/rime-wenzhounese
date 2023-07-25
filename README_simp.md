<h1 align="center">吴语·温州话<a rel="繁体中文" href="/README.md"><br><font size="4">繁体中文</font></a><br><a rel="license" href="http://creativecommons.org/licenses/by-nd/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/4.0/80x15.png" /></a></h1>

## 字典已完成收录，可正常输入单字<br>词典尚未完成最终收录，仍正在完善之中

[Rime](https://rime.im) 吴语-温州话输入方案

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
2.	[小學堂](https://xiaoxue.iis.sinica.edu.tw/ccdb)
3.	[拼字输入法](https://hanzi.unihan.com.cn/PinZi)
4.	[两分查字](http://zisea.com/zslf.htm)
5.	[中文简繁体转换](https://tool.lu/zhconvert/)
6.	[正则表达式测试](https://regexr-cn.com/)
7.	[異体字リスト](https://www.tobunken.go.jp/archives/%E7%95%B0%E4%BD%93%E5%AD%97%E3%83%AA%E3%82%B9%E3%83%88/)
8.	[Schema.yaml 詳解](https://github.com/LEOYoon-Tsaw/Rime_collections/blob/master/Rime_description.md)
9.	[鼠须管配置使用](https://blog.isteed.cc/post/squirrel-customization-2022/)

## 安装

1.	根据系统安装对应的[Rime输入法引擎](https://rime.im/download/)版本

-	Android系统安装使用可参阅[osfans/trime](https://github.com/osfans/trime)以及[SivanLaai/rime-pure](https://github.com/SivanLaai/rime-pure)
-	iOS系统安装使用可参阅[Hamster](https://github.com/imfuxiao/Hamster)

2.	将系统输入切换至Rime输入法

3.	在状态栏上右键Rime图标，点击`用戶文件夾`以开启
> 亦可手动打开Rime用户文件夹，路径如下：
>
> 【中州韻】 `~/.config/ibus/rime/`<br>
> 【小狼毫】 `%APPDATA%\Rime`<br>
> 【鼠鬚管】 `~/Library/Rime/`

2.	将以`*.yaml`结尾的文件均复制至`用戶資料夾`内

	-	`wenzhounese.custom.yaml`文件是针对原拼写方案的模糊音定制方案文件，使用后一定程度上可根据普通话拼音的逻辑进行输入
	-	对于模糊音定制方案文件可见[模糊音方案说明](/FuzzySoundList.md)
	-	注意：模糊音定制方案文件导入使用后将升高重码率，如果要只使用原拼写方案进行输入的话不导入此文件即可
	

3.	在状态栏上右键Rime图标，点击`輸入法設定`以打开启设定界面，勾选中`溫州話輸入法`以开启

4.	在状态栏上右键Rime图标，点击`重新部署`

5.	按下 `Control+｀` 或 `F4` （Rime默认快捷键），唤出方案选单，选择`溫州話輸入法`

6.	开始输入

## 简繁体字形转换

### 默认繁体字形原因

考虑到繁体字形保留的信息比简体字形要多，且繁转简比简转繁要**容易且不容易出错**很多，因此字词库在录入时均使用繁体字形。

### 如何输出简体字形

Rime输入法引擎自带繁简转换功能，具体步骤如下：
1.	切换至Rime输入法
2.	按下 `Control+｀` 或 `F4` （Rime默认快捷键），唤出方案选单，选择`溫州話輸入法`
3.	再次按下 `Control+｀` 或 `F4`，重新唤出方案选单
4.	再次选择`溫州話輸入法`，此时会进入下一级菜单
5.	选择`3. 漢字 → 汉字`，此时该选项会变为`3. 汉字 → 漢字`，即可开启简体字形输出
> 若需切换回繁体字形，重复上述步骤改回`3. 漢字 → 汉字`的状态即可<br>
> 注意：此简体字形输出更改行为为临时更改，在切换输入法后会重新回到繁体字形输出模式。

### 如何将简体字形输出设置为默认

1.	在状态栏上右键Rime图标点击`用戶文件夾`以开启
> 亦可手动打开Rime用户文件夹，路径如下：
>
> 【中州韻】 `~/.config/ibus/rime/`<br>
> 【小狼毫】 `%APPDATA%\Rime`<br>
> 【鼠鬚管】 `~/Library/Rime/`
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


## 许可证

<p align="center"><a rel="license" href="http://creativecommons.org/licenses/by-nd/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/4.0/88x31.png" /></a><br />本作品采用<a rel="license" href="http://creativecommons.org/licenses/by-nd/4.0/">知识共享署名-禁止演绎 4.0 国际许可协议 (CC BY-NC-ND 4.0)</a>进行许可。</p>

版权所有 © 2020-2023 Wolken (zwolken@foxmail.com | zharry@web.de)