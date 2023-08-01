<h1 align="center">吳語·溫州話<br><a rel="简体中文" href="/docs/README_simp.md"><font size="4">简体中文</font></a>　<a rel="網頁端" href="https://zwolken.github.io/rime-wenzhounese/"><font size="4">網頁端</font></a><br>

[![LICENSE](https://img.shields.io/badge/license-AGPL3.0-blue?style=for-the-badge)](https://github.com/ZWolken/rime-wenzhounese/blob/main/LICENSE)<br>
[![GitHub Repo stars](https://img.shields.io/github/stars/ZWolken/rime-wenzhounese?style=for-the-badge)](https://github.com/ZWolken/rime-wenzhounese)
[![GitHub all releases](https://img.shields.io/github/downloads/ZWolken/rime-wenzhounese/total?style=for-the-badge)](https://github.com/ZWolken/rime-wenzhounese/releases)
</h1>

# [Rime](https://rime.im) 吳語-溫州話輸入方案

字典根據沈克成-沈迦的拼音方案進行錄入。

**具體實現功能：**
-	**根據沈式拼音方案進行文字輸入**
-	**根據[模糊音方案規則](/docs/FuzzySoundList.md)按照普通話拼音邏輯進行文字輸入**
-	**可切換輸出為簡體字形或繁體字形（默認繁體字形）**
-	**根據拼音進行溫州話發音反查**

模糊音方案規則主要模糊了濁音的輔音叠寫，若有需要可導入模糊音文件以開啓。

拼寫方案及字詞典來源：
1.	温州话/沈克成,沈迦著.—宁波:宁波出版社,2004.11
	- ISBN 7-80602-811-0
2.	温州话:增补本/沈克成,沈迦著.—宁波:宁波出版社,2013.3
	- ISBN 978-7-5526-0708-6
-	注意：部分内容使用了OCR以及簡繁轉換工具，校對后仍可能會有錯誤存在，若發現錯誤敬請提交Issue説明。

參考資料：
1.	[漢典](https://www.zdic.net/)
2.	[小學堂|漢字古今字資料庫](https://xiaoxue.iis.sinica.edu.tw/ccdb)
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
-	未曾使用過小狼毫輸入法的Windows用戶可直接下載`*.exe`格式結尾的安裝包进行安裝使用。
-	壓縮包文件選`rime-wenzhounese`開頭的其一下載即可。
-	`trime-wenzhounese`開頭的壓縮包為Android系統安裝使用，也是選擇一個下載即可。
-	壓縮包下載完成後請解壓到可自行可操作的文件夾備用，其中的包含的全部yaml文件以及icon文件夾及文件夾內文件爲需要使用的。
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
	-	對於模糊音定制方案文件可見[模糊音方案説明](/docs/FuzzySoundList.md)
	-	注意：模糊音定制方案文件導入使用后將升高重碼率，如果要只使用原拼寫方案進行輸入的話不導入此文件即可。若已經導入且部署，刪除`wenzhounese.custom.yaml`文件後重新部署即可。

6.	在狀態欄上右鍵Rime圖標，點擊`輸入法設定`以打開啓設定界面，勾選中`溫州話`以開啓

7.	在狀態欄上右鍵Rime圖標，點擊`重新部署`

8.	按下<kbd>Ctrl</kbd>+<kbd>｀</kbd> 或 <kbd>F4</kbd>（Rime默認快捷鍵），喚出方案選單，選擇`溫州話`

9.	開始輸入

## 拼音反查

本輸入方案額外增加了拼音反查功能，可通過輸入普通話拼音來查詢具體某字的溫州話發音（采用沈氏拼音方式表示），具體步驟如下：

1.	將系統輸入切換至Rime輸入法，并且選擇`溫州話`輸入方案以激活

2.	按下鍵盤上的<kbd>｀</kbd>鍵，輸入拼音即可進行反查，若一個字存在多個讀音，則均會顯示


## 簡繁體字形轉換

### 默認繁體字形原因

考慮到繁體字形保留的信息比簡體字形要多，且繁轉簡比簡轉繁要**容易且不容易出錯**很多，因此字詞庫在錄入時均使用繁體字形。

### 如何臨時輸出簡體字形

Rime輸入法引擎自帶繁簡轉換功能，具體步驟如下：

1.	切換至Rime輸入法

2.	按下<kbd>Ctrl</kbd>+<kbd>｀</kbd> 或 <kbd>F4</kbd>（Rime默認快捷鍵），喚出方案選單，選擇`溫州話`

3.	再次按下<kbd>Ctrl</kbd>+<kbd>｀</kbd> 或 <kbd>F4</kbd>，重新喚出方案選單

4.	再次選擇`溫州話`，此時會進入下一級菜單

5.	選擇`3. 漢字 → 汉字`，此時該選項會變爲`3. 汉字 → 漢字`，即可開啓簡體字形輸出
	-	若需切換回繁體字形，重複上述步驟改回`3. 漢字 → 汉字`的狀態即可

-	注意：此簡體字形輸出更改行爲為臨時更改，在切換輸入法后會重新回到繁體字形輸出模式。
-	因程式相關限制，此項修改不會對拼音反查的簡繁字形起修改作用，具體修改方案請見後文。

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
26	  - name: simplification
27	    reset: 0
28	      # 0[默認缺省值]：輸出原字形（繁體）；1：啓用「繁→簡」轉換，輸出簡體字
29	    states: [ 漢字, 汉字 ]
```

4.	刪除第27行行首的`#`符號，修改成如下所示：
```yaml
    reset: 1
```

5.	保存文件更改

6.	在狀態欄上右鍵Rime圖標，點擊`重新部署`

7.	喚出方案選單，再次選擇`溫州話`

8.	此時已將簡體字形輸出設置爲默認狀態
	-	若需切換回默認繁體字形輸出，將即可`wenzhounese.schema.yaml`的第27行行首的`#`符號添加回即可。

-	因程式相關限制，此項修改不會對拼音反查的簡繁字形起修改作用，具體修改方案請見後文。

### 如何將拼音反查設置爲簡體字形

1.	在狀態欄上右鍵Rime圖標，點擊`輸入法設定`以打開啓設定界面，勾選中`袖珍简化字拼音`以開啓

	- 若在設定界面無法找到`袖珍简化字拼音`，請檢查`用戶文件夾`内是否有以下兩個文件：
		- pinyin_simp.schema.yaml
		- pinyin_simp.dict.yaml
	- 若沒有，請前往[rime/rime-pinyin-simp](https://github.com/rime/rime-pinyin-simp)下載補全文件

2.	使用`記事本`或`Visual Studio Code`等軟體打開`wenzhounese.schema.yaml`文件以備用編輯

3.	跳轉到第69行，具體代碼應如下：
```yaml
68	reverse_lookup:
69	  dictionary: luna_pinyin
70	  #dictionary: pinyin_simp
71	  #若需要繁體字形拼音反查：刪除上方luna_pinyin行前#字符，並用#字符注釋pinyin_simp行
72	  #若需要簡體字形拼音反查：刪除上方pinyin_simp行前#字符，並用#字符注釋luna_pinyin行
73	  prefix: "`"
```

4.	在69行行首添加`#`符號，並刪除第70行行首的`#`符號，修改成如下所示：
```yaml
69	  #dictionary: luna_pinyin
70	  dictionary: pinyin_simp
```

5.	保存文件更改

6.	在狀態欄上右鍵Rime圖標，點擊`重新部署`

7.	喚出方案選單，再次選擇`溫州話`

8.	此時的拼音反查已經設定爲簡體字形
	- 若需切換回默認繁體字形的拼音反查，將69行和70行行首的`#`符號添加恢復回到步驟3所示，再重新部署即可。

-	若不需要`袖珍简化字拼音`輸入方案，在拼音反查設定爲簡體字形成功后打開`輸入法設定`關閉即可，並不會影響拼音反查的簡體字形。

## 任務清單 To-Do List

- [x] 基礎字匯錄入（2004年版本）
- [ ] 基礎字匯更新（拼寫方案更新至2013年版本）
- [ ] 拓展字匯錄入（更新至《温州话字林》的2w+字头）
- [x] 基礎詞匯錄入（2013年版本）
- [ ] 拓展詞匯錄入（更新至《温州话辞典》的全部詞匯）
- [x] 模糊音規則編寫（基於2004年版本）
- [ ] 模糊音規則更新（基於2013年版本）
- [x] 輸入方案打包成輸入法安裝包（Windows端）

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
