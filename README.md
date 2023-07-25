<h1 align="center">吳語·溫州話<a rel="简体中文" href="/README_simp.md"><br><font size="4">简体中文</font></a><br><a rel="license" href="http://creativecommons.org/licenses/by-nd/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/4.0/80x15.png" /></a></h1>

## 字典已完成收錄，可正常輸入單字<br>詞典尚未完成最終收錄，仍正在完善之中

[Rime](https://rime.im) 吳語-溫州話輸入方案

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
7.	[異体字リスト](https://www.tobunken.go.jp/archives/%E7%95%B0%E4%BD%93%E5%AD%97%E3%83%AA%E3%82%B9%E3%83%88/)
8.	[Schema.yaml 詳解](https://github.com/LEOYoon-Tsaw/Rime_collections/blob/master/Rime_description.md)
9.	[鼠须管配置使用](https://blog.isteed.cc/post/squirrel-customization-2022/)

## 安裝

1.	根據系統安裝對應的[Rime輸入法引擎](https://rime.im/download/)版本

-	Android系統安裝使用可參閲[osfans/trime](https://github.com/osfans/trime)以及[SivanLaai/rime-pure](https://github.com/SivanLaai/rime-pure)
-	iOS系統安裝使用可參閲[Hamster](https://github.com/imfuxiao/Hamster)

2.	將系統輸入切換至Rime輸入法

3.	在狀態欄上右鍵Rime圖標，點擊`用戶文件夾`以開啓
> 亦可手動打開Rime用戶文件夾，路徑如下：
>
> 【中州韻】 `~/.config/ibus/rime/`<br>
> 【小狼毫】 `%APPDATA%\Rime`<br>
> 【鼠鬚管】 `~/Library/Rime/`

2.	將以`*.yaml`結尾的文件均複製至`用戶資料夾`内

	-	`wenzhounese.custom.yaml`文件是針對原拼寫方案的模糊音定制方案文件，使用後一定程度上可根據普通話拼音的邏輯進行輸入
	-	對於模糊音定制方案文件可見[模糊音方案説明](/FuzzySoundList.md)
	-	注意：模糊音定制方案文件導入使用后將升高重碼率，如果要只使用原拼寫方案進行輸入的話不導入此文件即可
	

3.	在狀態欄上右鍵Rime圖標，點擊`輸入法設定`以打開啓設定界面，勾選中`溫州話輸入法`以開啓

4.	在狀態欄上右鍵Rime圖標，點擊`重新部署`

5.	按下 `Control+｀` 或 `F4` （Rime默認快捷鍵），喚出方案選單，選擇`溫州話輸入法`

6.	開始輸入

## 簡繁體字形轉換

### 默認繁體字形原因

考慮到繁體字形保留的信息比簡體字形要多，且繁轉簡比簡轉繁要**容易且不容易出錯**很多，因此字詞庫在錄入時均使用繁體字形。

### 如何輸出簡體字形

Rime輸入法引擎自帶繁簡轉換功能，具體步驟如下：
1.	切換至Rime輸入法
2.	按下 `Control+｀` 或 `F4` （Rime默認快捷鍵），喚出方案選單，選擇`溫州話輸入法`
3.	再次按下 `Control+｀` 或 `F4`，重新喚出方案選單
4.	再次選擇`溫州話輸入法`，此時會進入下一級菜單
5.	選擇`3. 漢字 → 汉字`，此時該選項會變爲`3. 汉字 → 漢字`，即可開啓簡體字形輸出
> 若需切換回繁體字形，重複上述步驟改回`3. 漢字 → 汉字`的狀態即可<br>
> 注意：此簡體字形輸出更改行爲為臨時更改，在切換輸入法后會重新回到繁體字形輸出模式。

### 如何將簡體字形輸出設置爲默認

1.	在狀態欄上右鍵Rime圖標點擊`用戶文件夾`以開啓
> 亦可手動打開Rime用戶文件夾，路徑如下：
>
> 【中州韻】 `~/.config/ibus/rime/`<br>
> 【小狼毫】 `%APPDATA%\Rime`<br>
> 【鼠鬚管】 `~/Library/Rime/`
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


## 許可證

<p align="center"><a rel="license" href="http://creativecommons.org/licenses/by-nd/4.0/"><img alt="知識共享許可協議" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/4.0/88x31.png" /></a><br />本作品採用<a rel="license" href="http://creativecommons.org/licenses/by-nd/4.0/">姓名標示-非商業性-禁止改作 4.0 國際 (CC BY-NC-ND 4.0)</a>進行許可。</p>

>簡體中文：知识共享署名-禁止演绎 4.0 国际许可协议

版權所有 © 2020-2023 Wolken (zwolken@foxmail.com | zharry@web.de)