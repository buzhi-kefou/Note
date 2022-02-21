# Markdown
## 简介
Markdown是一种轻量级标记语言，允许人们使用易读易写的纯文本格式来编辑文档。
## 标题
### \#
```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
### = -
```markdown
一级标题
=======
二级标题
-------
```
## 段落
换行用两个空格加回车  
段落用一个或多个空白行来分隔
### 字体
```markdown
*斜体*
_斜体_
**粗体**
__粗体__
***粗斜体***
___粗斜体___
```
### 分隔线
三个以上的星号、减号、底线,中间可以插入空格
```markdown
***
---
___
* * *
- - -
_ _ _
```
### 删除线
左右两个波浪线
```markdown
~~delete~~
```
### 下划线
u标签
```markdown
<u>underline</u>
```
### 脚注
```markdown
[^word]
[^word]:The meaning of this word.
```
## 列表
有序列表 * + -
无序列表 n.
```markdown
* 第一项
* 第二项
* 第三项
1. 第一项
2. 第二项
3. 第三项
```
## 区块
```markdown
> 开头
> 中间
> 结尾
```
## 代码
一个tab或四个空格  

    System.out.println("hello world");
***
一对反引号  

`
function hello(){
    console.log("rainbow fart");
}
`
---
三对反引号

```sql
select sysdate from dual
```
## 链接
```markdown
[链接名称](链接地址 "可选标题")
<链接地址>
```
## 图片
感叹号方括号圆括号
```markdown
![alt 属性文本](图片地址 "可选标题")
```
## 表格
| 表头 | 表头 | 表头 |
| --- | --- | --- |
| 单元格 | 单元格 | 单元格 |
## 转义
\
