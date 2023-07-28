<h1 align="center">吳語·溫州話<a rel="简体中文" href="/README_simp.md"><br><font size="4">简体中文</font></a><br>

[![LICENSE](https://img.shields.io/badge/license-AGPL3.0-blue?style=for-the-badge)](https://github.com/ZWolken/rime-wenzhounese/blob/main/LICENSE)<br>
[![GitHub Repo stars](https://img.shields.io/github/stars/ZWolken/rime-wenzhounese?style=for-the-badge)](https://github.com/ZWolken/rime-wenzhounese)
[![GitHub all releases](https://img.shields.io/github/downloads/ZWolken/rime-wenzhounese/total?style=for-the-badge)](https://github.com/ZWolken/rime-wenzhounese/releases)

# [Rime](https://rime.im) 吳語-溫州話輸入方案

字典根據沈克成-沈迦的拼音方案進行錄入。

模糊音方案規則主要模糊了濁音的輔音叠寫，若有需要可導入模糊音文件以開啓。

拼寫方案及字詞典來源：
1.	温州话/沈克成,沈迦著.—宁波:宁波出版社,2004.11
	- ISBN 7-80602-811-0
2.	温州话:增补本/沈克成,沈迦著.—宁波:宁波出版社,2013.3
	- ISBN 978-7-5526-0708-6
> 注意：部分内容使用了OCR以及簡繁轉換工具，校對后仍可能會有錯誤存在，若發現錯誤敬請提交Issue説明。

參考資料：
1.	[漢典](https://www.zdic.net/)
2.	[小學堂](https://xiaoxue.iis.sinica.edu.tw/ccdb)
3.	[拼字输入法](https://hanzi.unihan.com.cn/PinZi)
4.	[两分查字](http://zisea.com/zslf.htm)
5.	[中文简繁体转换](https://tool.lu/zhconvert/)
6.	[正则表达式测试](https://regexr-cn.com/)
7.	[汉字字符集编码查询](https://www.qqxiuzi.cn/bianma/zifuji.php)
8.	[異体字リスト](https://www.tobunken.go.jp/archives/%E7%95%B0%E4%BD%93%E5%AD%97%E3%83%AA%E3%82%B9%E3%83%88/)
9.	[Schema.yaml 詳解](https://github.com/LEOYoon-Tsaw/Rime_collections/blob/master/Rime_description.md)
10.	[鼠须管配置使用](https://blog.isteed.cc/post/squirrel-customization-2022/)

## 安裝

1.	根據系統下載安裝對應的[Rime輸入法引擎](https://rime.im/download/)版本

-	Android系統安裝使用可參閲[osfans/trime](https://github.com/osfans/trime)以及[SivanLaai/rime-pure](https://github.com/SivanLaai/rime-pure)
-	iOS系統安裝使用可參閲[Hamster](https://github.com/imfuxiao/Hamster)

2.	從[Release（發行版發佈頁）](https://github.com/ZWolken/rime-wenzhounese/releases/latest)下載最新版本的數據文件。
-	壓縮包文件或者全部的`*.yaml`結尾的文件選一者全部下載即可。
-	壓縮包下載完成后請解壓到可自行可操作的文件夾備用。
-	<details>
	<summary>不會解壓縮文件？</summary>
	請查閱<a href="https://[www.runoob.com/](https://blog.csdn.net/weixin_44168217/article/details/96311980)">壓縮包解壓教程</a>。
	</details>

3.	將系統輸入切換至Rime輸入法

4.	在狀態欄上右鍵Rime圖標，點擊`用戶文件夾`以開啓
-	<details>
	<summary>亦可手動打開Rime用戶文件夾，路徑如下：</summary>
	【中州韻】<code>~/.config/ibus/rime/</code><br>
	【小狼毫】<code>%APPDATA%\Rime</code><br>
	【鼠鬚管】<code>~/Library/Rime/</code>
	</details>

5.	將以`*.yaml`结尾的文件均複製至`用戶資料夾`内

	-	`wenzhounese.custom.yaml`文件是針對原拼寫方案的模糊音定制方案文件，使用後一定程度上可根據普通話拼音的邏輯進行輸入
	-	對於模糊音定制方案文件可見[模糊音方案説明](/FuzzySoundList.md)
	-	注意：模糊音定制方案文件導入使用后將升高重碼率，如果要只使用原拼寫方案進行輸入的話不導入此文件即可

6.	在狀態欄上右鍵Rime圖標，點擊`輸入法設定`以打開啓設定界面，勾選中`溫州話輸入法`以開啓

7.	在狀態欄上右鍵Rime圖標，點擊`重新部署`

8.	按下<kbd>Ctrl</kbd>+<kbd>｀</kbd> 或 <kbd>F4</kbd>（Rime默認快捷鍵），喚出方案選單，選擇`溫州話輸入法`

9.	開始輸入

## 簡繁體字形轉換

### 默認繁體字形原因

考慮到繁體字形保留的信息比簡體字形要多，且繁轉簡比簡轉繁要**容易且不容易出錯**很多，因此字詞庫在錄入時均使用繁體字形。

### 如何輸出簡體字形

Rime輸入法引擎自帶繁簡轉換功能，具體步驟如下：
1.	切換至Rime輸入法

2.	按下<kbd>Ctrl</kbd>+<kbd>｀</kbd> 或 <kbd>F4</kbd>（Rime默認快捷鍵），喚出方案選單，選擇`溫州話輸入法`

3.	再次按下<kbd>Ctrl</kbd>+<kbd>｀</kbd> 或 <kbd>F4</kbd>，重新喚出方案選單

4.	再次選擇`溫州話輸入法`，此時會進入下一級菜單

5.	選擇`3. 漢字 → 汉字`，此時該選項會變爲`3. 汉字 → 漢字`，即可開啓簡體字形輸出
> 若需切換回繁體字形，重複上述步驟改回`3. 漢字 → 汉字`的狀態即可<br>
> 注意：此簡體字形輸出更改行爲為臨時更改，在切換輸入法后會重新回到繁體字形輸出模式。

### 如何將簡體字形輸出設置爲默認

1.	在狀態欄上右鍵Rime圖標點擊`用戶文件夾`以開啓
-	<details>
	<summary>亦可手動打開Rime用戶文件夾，路徑如下：</summary>
	【中州韻】<code>~/.config/ibus/rime/</code><br>
	【小狼毫】<code>%APPDATA%\Rime</code><br>
	【鼠鬚管】<code>~/Library/Rime/</code>
	</details>

2.	使用`記事本`或`Visual Studio Code`等軟體打開`wenzhounese.schema.yaml`文件以備用編輯

3.	跳轉到第23行，具體代碼應如下：
```yaml
22  - name: simplification
23    #reset: 1   # 0[默認缺省值]：輸出原字形（繁體）；1：啓用「繁→簡」轉換，輸出簡體字
24    states: [ 漢字, 汉字 ]
```

4.	刪除第23行行首的`#`符號，修改成如下所示：
```yaml
reset: 1   # 0[默認缺省值]：輸出原字形（繁體）；1：啓用「繁→簡」轉換，輸出簡體字
```

5.	保存文件更改

6.	在狀態欄上右鍵Rime圖標，點擊`重新部署`

7.	喚出方案選單，再次選擇`溫州話輸入法`

8.	此時已將簡體字形輸出設置爲默認狀態
> 若需切換回默認繁體字形輸出，將即可`wenzhounese.schema.yaml`的第23行行首的`#`符號添加回即可。

## 任務清單 To-Do List

- [x] 基礎字匯錄入（2004年版本）
- [ ] 基礎字匯更新（拼寫方案更新至2013年版本）
- [ ] 拓展字匯錄入（更新至《温州话字林》的2w+字头）
- [x] 基礎詞匯錄入（2013年版本）
- [ ] 拓展詞匯錄入（更新至《温州话辞典》的全部詞匯）
- [x] 模糊音規則編寫（基於2004年版本）
- [ ] 模糊音規則更新（基於2013年版本）
- [ ] 輸入方案打包成輸入法安裝包

**錄入量巨大**，**目前完成時間未知**，若有想幫忙者可通過[zwolken@foxmail.com](mailto:zwolken@foxmail.com)郵箱地址找到我進行後續聯係。感激不盡！

## 許可 & 許可證

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

本項目已獲得沈克成先生的授權，可使用沈克成先生所出版書籍的内容。<br>
版權所有 © 2023 Wolken (zwolken@foxmail.com | zharry@web.de)
