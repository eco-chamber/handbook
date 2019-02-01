# 如何修改行為守則 (Code of Conduct)

Eco-Chamber 的文檔是基於 [Sphinx](http://www.sphinx-doc.org/en/master/) 文檔產生器生成， Sphinx 是一個輕量、快速，並且基於 Python 的文檔生成器，可以用來撰寫 API 文件、專案說明和交接文件等等，也提供了多種[背景樣式](http://www.sphinx-doc.org/en/stable/theming.html)可供使用，連 Python 本身的[文檔](https://docs.python.org/3/)也是利用 Sphinx 生成的噢。


### 一、git clone 本專案

打開終端機輸入指令，或使用任何一個 GUI 軟體都可以，例如： [GitHub Desktop](https://desktop.github.com/)。

```shell
$ git clone https://github.com/eco-chamber/handbook.git
```

----------------------

### 二、安裝依賴套件

`cd` 進 handbook 專案目錄，安裝依賴套件。

- recommonmark
- Sphinx
- sphinx_rtd_theme
- sphinx-markdown-tables

```shell
# using pip
$ pip install -r requirements.txt

# using pipenv
$ pipenv install -r requirements.txt

# using conda
while read requirement; do conda install --yes $requirement; done < requirements.txt
```

----------------------

### 三、文檔目錄結構

![](https://i.imgur.com/UGrCf5s.png)

會改動到的只有 
- [index.rst](https://github.com/eco-chamber/handbook/blob/master/index.rst)
- [./topic_folders](https://github.com/eco-chamber/handbook/tree/master/topic_folders) 目錄底下的東西

`.rst` 結尾的檔案用來更改檔案目錄，打開 `index.rst`，會看到：

```
.. toctree::
   :maxdepth: 2   
   :glob:
   :caption: General Resources

   topic_folders/assessment/index.rst
   topic_folders/communications/index.rst
   topic_folders/for_instructors/index.rst
   topic_folders/instructor_development/index.rst
   topic_folders/instructor_training/index.rst
   topic_folders/lesson_development/index.rst
   topic_folders/maintainers/index.rst
   topic_folders/policies/index.rst
   topic_folders/regional_communities/index.rst
   topic_folders/hosts_instructors/index.rst
   topic_folders/workshop_administration/index.rst
   topic_folders/governance/index.rst
```

對照文檔網頁會看到
![](https://i.imgur.com/4cFJbBQ.png)

是不是很熟悉~ 檔案目錄都呈現在這裡了。

----------------------

### 四、修改文字內容

進入 `topic_folders` 會看到很多資料夾，裡面包含了 Markdown 文件和定義文檔目錄結構的 `index.rst`。

![](https://i.imgur.com/KGtTafh.png)

對應到網站則是呈現

![](https://i.imgur.com/DMgGFkH.png)

打開文字編輯器開始修改文件即可~

----------------------

### 五、產生 Html 靜態檔案

`cd` 回去專案根目錄，輸入命令產生靜態檔案

```shell
$ make html
```

----------------------

### 六、上傳至 GitHub

輸入 git 指令上傳專案。

```shell
$ git add .                       # 加入改動的文件
$ git commit -m "add new post"    # commit 訊息
$ git push                        # 推送至 GitHub
```