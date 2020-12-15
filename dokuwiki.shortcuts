
## 基本文本格式语法

```
**粗体**
//斜体//
__下划线__
''等宽字体''
**__//''多种格式合用''//__**
<sub>上标</sub>
<sup>下标</sup>
<del>删除线</del>
新段落：两段间插入空行
强制换行：\\加上空格或回车，不加空格或回车的\\是无效的

```

## 链接语法

```
外部链接：

http://www.google.com
www.google.com
[[链接地址|链接显示名称]]
<andi@splitbrain.org>


内部链接：

[[页面名称]]
[[页面名称|链接显示名称]]
[[命名空间:页面名称|链接显示名称]]
[[页面名称#标题|链接显示名称]]


链接到其他Wiki：

[[interwiki|链接显示名称]] #链接到https://www.dokuwiki.org/wiki%3Ainterwiki
[[wp>Wiki]] #链接到https://en.wikipedia.org/wiki/Wiki

图像链接：

#显示图片wiki:dokuwiki-128.png，链接至http://php.net
[[http://php.net|{{wiki:dokuwiki-128.png}}]]
```


## 脚注

```
((脚注的内容)) #脚注会自动给出编号
```

标题段落

```
====== H1标题 ======
===== H2标题 =====
==== H3标题 ====
=== H4标题 ===
== H5标题 ==
----- #4个或以上连续-，水平分割线

```

多媒体文件
```
{{wiki:dokuwiki-128.png}} #原始大小
{{wiki:dokuwiki-128.png?50}} #指定宽度50
{{wiki:dokuwiki-128.png?200*50}} #指定宽度200和高度50
{{http://php.net/images/php.gif?200x50}} #外部图片指定宽度和高度
{{ wiki:dokuwiki-128.png}} #右侧对齐
{{wiki:dokuwiki-128.png }} #左侧对齐
{{ wiki:dokuwiki-128.png }} #中间对齐
{{ wiki:dokuwiki-128.png |这是图像的名字}} #中间对齐，定义图片名称
支持的媒体格式：
图像：gif, jpg, png
视频：webm, ogv, mp4
音频：ogg, mp3, wav
flash：swf
如果添加的文件不是所支持的格式，会显示一个连接。
```

## 列表

```
#前面需要带2个空格，缩进为2个空格
  * 不带编号的列表
  * 第二项
    * 下一层
  * 第三项

  - 带编号的列表
  - 第二项
    - 下一层
  - 第三项

```

## 引用

```
I think we should do it
> No we shouldn't
>> Well, I say we should
> Really?
>> Yes!
>>> Then lets do it!
```
表格

```
#表头蓝色，合并水平单元格只需将后一个需合并掉的单元格置为空，如第二行
^ Heading 1 ^ Heading 2 ^ Heading 3 ^
| Row 1 Col 1 | Row 1 Col 2 | Row 1 Col 3 |
| Row 2 Col 1 | some colspan (note the double pipe) ||
| Row 3 Col 1 | Row 3 Col 2 | Row 3 Col 3 |

#垂直标题蓝色
| ^ Heading 1 ^ Heading 2 ^
^ Heading 3 | Row 1 Col 2 | Row 1 Col 3 |
^ Heading 4 | no colspan this time | |
^ Heading 5 | Row 2 Col 2 | Row 2 Col 3 |

#垂直合并
^ Heading 1 ^ Heading 2 ^ Heading 3 ^
| Row 1 Col 1 | this cell spans vertically | Row 1 Col 3 |
| Row 2 Col 1 | ::: | Row 2 Col 3 |
| Row 3 Col 1 | ::: | Row 2 Col 3 |

#不同的对齐方式
^ Table with alignment ^^^
| right| center |left |
|left | right| center |
| xxxxxxxxxxxx | xxxxxxxxxxxx | xxxxxxxxxxxx |

```

无格式块

```
<nowiki>无格式的内容</nowiki>
%%无格式的内容%%

```

代码块

```
代码内容 #2个及以上空格开头
<code>代码内容</code>
<file>代码内容</file>


代码高亮:

<code java>Java代码</code java>
<file java>Java代码</file java>

#支持语言：4cs, 6502acme, 6502kickass, 6502tasm, 68000devpac, abap, actionscript-french, actionscript, actionscript3, ada, algol68, apache, applescript, asm, asp, autoconf, autohotkey, autoit, avisynth, awk, bascomavr, bash, basic4gl, bf, bibtex, blitzbasic, bnf, boo, c, c_loadrunner, c_mac, caddcl, cadlisp, cfdg, cfm, chaiscript, cil, clojure, cmake, cobol, coffeescript, cpp, cpp-qt, csharp, css, cuesheet, d, dcs, delphi, diff, div, dos, dot, e, epc, ecmascript, eiffel, email, erlang, euphoria, f1, falcon, fo, fortran, freebasic, fsharp, gambas, genero, genie, gdb, glsl, gml, gnuplot, go, groovy, gettext, gwbasic, haskell, hicest, hq9plus, html, html5, icon, idl, ini, inno, intercal, io, j, java5, java, javascript, jquery, kixtart, klonec, klonecpp, latex, lb, lisp, llvm, locobasic, logtalk, lolcode, lotusformulas, lotusscript, lscript, lsl2, lua, m68k, magiksf, make, mapbasic, matlab, mirc, modula2, modula3, mmix, mpasm, mxml, mysql, newlisp, nsis, oberon2, objc, objeck, ocaml-brief, ocaml, oobas, oracle8, oracle11, oxygene, oz, pascal, pcre, perl, perl6, per, pf, php-brief, php, pike, pic16, pixelbender, pli, plsql, postgresql, povray, powerbuilder, powershell, proftpd, progress, prolog, properties, providex, purebasic, pycon, python, q, qbasic, rails, rebol, reg, robots, rpmspec, rsplus, ruby, sas, scala, scheme, scilab, sdlbasic, smalltalk, smarty, sql, systemverilog, tcl, teraterm, text, thinbasic, tsql, typoscript, unicon, uscript, vala, vbnet, vb, verilog, vhdl, vim, visualfoxpro, visualprolog, whitespace, winbatch, whois, xbasic, xml, xorg_conf, xpp, yaml, z80, zxbasic



可下载的代码块:

<file java 文件名>
文件内容
</file>
#使用-标记语言种类则不会高亮显示
<code - 文件名>
文件内容
</code>

```

## 嵌入HTML及PHP

```

#可使用大写标签，如果内嵌小写的标签
<html>HTML内容</html>
<php>PHP内容</php>

```