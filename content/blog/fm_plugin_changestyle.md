+++
author = "Wayne"
categories = ["TeComm"]
date = "2016-04-05T13:40:59+08:00"
description = "批量更改样式标签的 FrameMaker 插件"
featured = ""
featuredalt = ""
featuredpath = ""
linktitle = ""
title = "FrameMaker 插件 ChangeStyles 的安装和使用"
type = "post"
url = "/2016/04/05/fm-plugin-changestyles"

+++
[ChangeStylesInstaller]: http://pan.baidu.com/s/1jInOy7W
[FM_Menu_ChangeStyles]: http://c.picphotos.baidu.com/album/s%3D1400%3Bq%3D90/sign=cc7e26639752982201333dc7e7fa40ba/6609c93d70cf3bc71560d748d600baa1cd112a35.jpg
[FM_DB_ChangeStyles]: https://raw.githubusercontent.com/wayneko/images/master/201604/FM_DB_ChangeStyles.png
[FM_EG_Find]: http://e.picphotos.baidu.com/album/s%3D1400%3Bq%3D90/sign=144d15bd2af5e0feea188d056c500fd9/9f2f070828381f300d76970dae014c086e06f023.jpg
[FM_EG_Change]: http://d.picphotos.baidu.com/album/s%3D1000%3Bq%3D90/sign=a982e285758b4710ca2ff9ccf3fef88c/6a63f6246b600c339467c46c1d4c510fd9f9a173.jpg
[FM_M_AlertMessage]: http://d.picphotos.baidu.com/album/s%3D1000%3Bq%3D90/sign=7945ff820e24ab18e416e53705caddbc/e850352ac65c10387860d466b5119313b07e8973.jpg
[FM_DB_ChangeStyles_CharStyle]: http://d.picphotos.baidu.com/album/s%3D1000%3Bq%3D90/sign=48026056d262853596e0d621a0df4db7/728da9773912b31b6303d78d8118367adab4e123.jpg
[FM_EG_Find_Char]: http://b.picphotos.baidu.com/album/s%3D1000%3Bq%3D90/sign=a7ca767a3a6d55fbc1c672265d12743b/4034970a304e251f1497fe5ca086c9177f3e5335.jpg
[FM_EG_Change_Char]: http://f.picphotos.baidu.com/album/s%3D1000%3Bq%3D90/sign=215541921a950a7b71354ac43ae159a8/48540923dd54564eff05fe9db4de9c82d1584f35.jpg
[FM_Sample_Document_Updated5]: https://raw.githubusercontent.com/wayneko/images/master/201604/FM_Sample_Document_Updated5.png
# 前言

使用 FrameMaker 写作的小朋友经常会有这样的需求：一段文本已经应用了某种段落标签（Paragraph Tag）或字符标签（Character Tag），现在要改成另一种段落标签或字符标签。

测试图片
![Image of Sample Document after 5th Update][FM_Sample_Document_Updated5]

例如，原来有个二级标题，段落标签是 *h2* ，现在这个二级标题要降为三级标题，需要应用段落标签 *h3* 。我只需要将光标放在二级标题之中，然后单击 Paragraph Tag Catalog（段落标签目录）面板中的 *h3* 标签就行了。又如，原来有一个词语应用了斜体字符标签，现在要改成粗体，只需要选中这个词语，然后在 Character Tag Catalog（字符标签目录）面板中单击粗体对应的字符标签即可。

现在问题来了，如果我要更改标签的段落或词语是几十个甚至上百个呢？当对一批旧文档应用新模板时，这是一个典型的需求。手动逐一更改显然是让人无法接受的。但版本 11 及以前的 FrameMaker 并没有批量更改标签的功能。幸运的是，我们可以利用一款 FrameMaker 插件来完成这项工作，这款插件的名字叫做 ChangeStyles。

# 安装 ChangeStyles

1. 下载 [ChangeStyles][ChangeStylesInstaller]（文件大小：74KB）。  
   ChangeStyles2.zip 文件下载到电脑上。
2. 解压 ChangeStyles2.zip 到当前位置。  
   解压后出现名为 ChangeStyles2 的文件夹。
3. 将文件夹 ChangeStyles2 中的 ChangeStyleMenu.jsx 和子文件夹 ChangeStyle 拷贝到以下文件夹：  
   *C:\Program Files (x86)*\Adobe\AdobeFrameMaker11\startup（将斜体部分替换为你电脑上的路径）
4. 安装完毕。

# 验证安装结果

要验证 ChangeStyles 插件是否安装成功，请启动 FrameMaker，选择 **File > Utilities**，如果能看到 **Change Styles** 命令，就表示安装成功。

# 使用 ChangeStyles

1. 启动 FrameMaker。选择 **File > Utilities > Change Styles**。  
   ![Image of Change Styles Menu][FM_Menu_ChangeStyles]  
   Change Styles 对话框出现。  
   ![Image of Change Styles Dialog Box][FM_DB_ChangeStyles] 
2. 在 Change Styles 对话框的 Styles 区块中，按需采取以下操作：  
   * 如需批量更改段落样式，选择 **Para Style**。
   * 如需批量更改字符样式，选择 **Char Style**。
   * 如需批量更改表格样式，选择 **Table Style**。
3. 在 Change Styles 对话框的 Change From 区块中：  
   a. 从 **Find** 下拉菜单中选择要更改的标签。  
   b. 从 **Change** 下拉菜单中选择要应用的新标签。
4. 在 Change Styles 对话框中单击 **Change**。

# 用法示例

本示例将演示批量更改段落标签和字符标签。示例文件中原有两个二级标题和两个三级标题，现需要在一级标题和二级标题之间插入一个级别，因此原来的二级标题和三级标题都需要降一级。另外，示例文件中斜体字符应用了 *emphasis* 字符标签，现需要全部更改为粗体字符标签 *ui.control* 。

1. 打开示例文件。  
   示例文件显示在编辑窗口中。  
   ![Image of Sample Document][FM_Sample_Document]
2. 选择 **File > Utilities > Change Styles**。  
   Change Styles 对话框出现。
3. 在 Change Styles 对话框的 Change From 区块中：  
   a. 从 **Find** 下拉菜单中选择要更改的标签 *heading.3* 。  
      ![Image of Find Field][FM_EG_Find]  
   b. 从 **Change** 下拉菜单中选择要应用的新标签 *heading.4* 。  
      ![Image of Change Field][FM_EG_Change] 
4. 在 Change Styles 对话框中单击 **Change**。  
   Script Alert 对话框出现，告知用户一共更改了多少个标签实例。  
   ![Image of Script Alert Message][FM_M_AlertMessage]  
   示例文件中的三级标题已全部更改为四级标题。  
   ![Image of Sample Document after 1st Update][FM_Sample_Document_Updated1]
5. 在 Script Alert 对话框中单击 **OK**，然后选择 **File > Utilities > Change Styles**。  
   Change Styles 对话框出现。
6. 在 Change Styles 对话框的 Change From 区块中：  
   a. 从 **Find** 下拉菜单中选择要更改的标签 *heading.2* 。  
   b. 从 **Change** 下拉菜单中选择要应用的新标签 *heading.3* 。  
7. 在 Change Styles 对话框中单击 **Change**。  
   Script Alert 对话框出现，告知用户一共更改了多少个标签实例。示例文件中的二级标题已全部更改为三级标题。  
   ![Image of Sample Document after 2nd Update][FM_Sample_Document_Updated2]
8. 在 Script Alert 对话框中单击 **OK**，然后选择 **File > Utilities > Change Styles**。  
   Change Styles 对话框出现。
9. 在 Change Styles 对话框的 Styles 区块中，选择 **Char Style**。  
   ![Image of Change Styles Dialog Box for Character Style][FM_DB_ChangeStyles_CharStyle] 
10. 在 Change Styles 对话框的 Change From 区块中：  
   a. 从 **Find** 下拉菜单中选择要更改的标签 *emphasis* 。  
      ![Image of Find Field for Character][FM_EG_Find_Char]  
   b. 从 **Change** 下拉菜单中选择要应用的新标签 *ui.control* 。  
      ![Image of Change Field for Character][FM_EG_Change_Char] 
11. 在 Change Styles 对话框中单击 **Change**。  
   Script Alert 对话框出现，告知用户一共更改了多少个标签实例。示例文件中的 *emphasis* 字符已全部更改为 *ui.control* 字符。  
   ![Image of Sample Document after 3rd Update][FM_Sample_Document_Updated3]
12. 对 New Heading 1.1 应用段落标签 *heading.2* 。  
      任务完成。  
      ![Image of Sample Document after 4th Update][FM_Sample_Document_Updated4]

# 技巧与提示

* 在打开的文件中使用 Change Styles 时，作用范围是当前文件。在打开的书籍使用 Change Styles 时，作用范围是当前书籍中的所有文件。
* 当在书籍中使用 Change Styles，请注意，对话框的 **Find** 下拉菜单中可选的所有标签取自书籍中第一个文件，因此，我们要确保书籍中的第一个文件包含所有需要用到的标签。此外，**Find** 下拉菜单中的标签顺序并非按字母排序，而是按照标签在第一个文件中出现的先后顺序排序的，因此，为了方便查找，建议工作时新建一个示例文件并添加到书籍最上方，该示例文件中含有依次应用了各种标签的示例文本。

测试图片
![Image of Sample Document after 5th Update][FM_Sample_Document_Updated5]