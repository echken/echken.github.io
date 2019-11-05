---
layout: post
title: "Editor and Shell"
date: 2019-04-23 08:00:00 +0000
categories: Tools
tags: Tools
--- 

### 1. ***vim 自配置最常用快捷键..***  

快捷键|说明  
---|---|
, |Leader Key
<leader>n | 打开/关闭代码资源管理器
<leader>t | 打开/关闭函数列表
<leader>a |.h .cpp 文件切换
<leader>y |拷贝函数声明
<leader>p |生成函数实现
<leader>w |单词跳转
<leader>A |Ack搜索当前目录下的文本
<leader>g |显示git仓库提交记录
<leader>G |显示当前文件提交记录
<leader>gg |显示当前文件在某个commit下的完整内容
<leader>ff |语法错误自动修复(FixIt)
  <c-p> |切换到上一个buffer
  <c-n> |切换到下一个buffer
  <leader>d |删除当前buffer
  <leader>D |删除当前buffer外的所有buffer
  vim |运行vim编辑器时,默认启动开始页面
  <F5> |显示语法错误提示窗口
  <F7> |启用markdown实时预览
  <F8> |关闭markdown实时预览
  <F9> |显示上一主题
  <F10> |显示下一主题
  <leader>l |按竖线对齐
  <leader>= |按等号对齐
  Ya |复制行文本到字母a
  Da |剪切行文本到字母a
  Ca |改写行文本到字母a
  rr |替换文本
  <leader>r |全局替换，目前只支持单个文件
  gcc |注释代码
  gcap |注释段落
  vif |选中函数内容
  dif |删除函数内容
  cif |改写函数内容
  vaf |选中函数内容（包括函数名 花括号）
  daf |删除函数内容（包括函数名 花括号）
  caf |改写函数内容（包括函数名 花括号）
  fa |查找字母a，然后再按f键查找下一个
  <c-x><c-o> |Emoji补全

  * <leader>U  转到函数实现, 失效...??? gotofun 实现只写了cpp后缀, cc没写. 改为cc以后可以征程跳转  

### 2. ***gtags_scope***  
  gutentags-plus key map: 引用数据库.. 跳转   

  快捷 | means  
  ---|--- 
  <leader>cg | 查看光标下符号的定义  
  <leader>cs | 查看光标下符号的引用  
  <leader>cc | 查看有哪些函数调用了该函数  
  <leader>cf | 查找光标下的文件 包含那些文件 
  <leader>ci | 查找哪些文件 include 了本文件
  <leader>ct |  GscopeFind t
  <leader>ce |  GscopeFind e
  <leader>cd |  GscopeFind d 该函数调用了那些函数.
  <leader>ca |  GscopeFind a 
  <leader>ck |  GscopeKill 

### ***3. 代码对齐***   
  tabular:  刚才在Linuxtoy上发现一个很好用的Vim插件:tabular，下载试用了一下，确实很方便。 对于程序员来说，都希望代码看着整齐一点，tabular就是实现代码对齐的。比如好几行的变量赋值语句，变量名长短"参差不齐"，有时候会习惯手动调整，让赋值的"="对齐。其他时候，比如括号的对齐。 随手挑了一段代码试了一下：
   
  将光标移动到第7行，输入 :Tab /{ 将会根据 "{" 对齐接下来的几行代码(貌似 tabular 可以自动识别"作用域"，只处理7 – 15 行之间的代码)，像这样： 
    第8行代码最长，所以会根据其"{" 调节其他代码行~ 还可以根据其他符号对齐，
      
      :Tab /[symbol_to_align]
      当然这种格式调整也要根据情况使用，有的时候也不一定能达到好的效果。
      
      
### ***4.leaderf***    
      基本实在当前项目目录下搜寻!!! 包含其他文件加???   
      key | means  
      ---|---  
      <leader>b | LeaderfBuf
      <leader>f | LeaderfFunction!
      <leader>F | LeaderfFile
      <leader>m | LeaderMru
      <leader>T | LeaderBufTag!
      C-f       | Leaderf! rg -e expand("<cword>")
      C-b       | Leaderf! rg -F --current-buffer -e expand("<cword>")
      <leader>fr| Leaderf! gtags -r expand("<cword>") --auto-jump
      <leader>fd| ~~~~ -d ~~~~~
      <leader>fo| Leaderf! gtags --recall ""
      <leader>fn| Leaderf! gtags --next ""
      <leader>fp| Leaderf! gtags --previous ""

### ***5. easymotion***   
      ***原生跳转***  
      G：到文件尾
      numG：移动光标到指定的行（num）。（比如 10G 就是到第 10 行）   
#h/j/k/l  左/上/下/右 跳转# line/colom/colom/line

      gg：到文件首  
      zz 让光标所在的行居屏幕中央  
      zt 让光标所在的行居屏幕最上一行 t=top  
      zb 让光标所在的行居屏幕最下一行 b=bottom  
      H,L,M 功能类似   

      f
    everf????　　
    
    ***easymotion***   
    key | means 
    --- | ---
    <leader>w/W         | 
    <leader><leader>w/W |
    <leader><leader>e/E | 
    <leader><leader>b/B | 
    <leader><leader>ge/gE|
    <leader><leader>f/F/t/T{char} | 单个字母搜索,跳转
    <leader><leader>j | line downward
    <leader><leader>k | line upward
    <leader><leader>n/N| 最近搜索结果 / 或者 ?, foward/backward
    <leader><leader>s  | 　向前或向后搜索字符（大小写好像忽略）  
      
    window/ pane 之间的快速跳转移动?????  
    
### ***6. YCM***  
    
    key | means 
    --- | --- 
    <leader>u |转到函数声明
    <leader>i |转到函数实现
    <leader>o |打开include文件
    <leader>jd| declaration/definition
    <leader>ff| fixit
    F5        | 显示diags 结果  
    
### ***7. quickfix***  
    
    quickfix的:cnext和:cprevious命令(cn cp)   
    
### ***8. 选择&&(曾/删除/改/替换)***   
    
    ***选择:***   
    vim原生选择:  
    选择： 
    选中{}中间的内容,不包括{}  
    va{ 选中{}中间内容，包括{}  
    选中()中间内容  
    vi< 选中<>中间内容   
    vi[ 选中[]中间内容  
    vit 选中中间的内容  
    vi” 选中”"中间内容  
    vi’ 选中”中间的内容、  
    vis 选中一个句子  
    vib 选中一个block  
    viw 选中一个单词  
    vip 选中一个段落
    vG   选中光标到结尾
    v1G  选中第一行到光标  
    vwww，会高亮光标前面的三个词。Vjj将会高亮当前行以及下面两行.     
    
    文本对象 |  操作范围  
    ---   | ---
    aw  |光标所在单词加上一个空格
    iw  |光标所在单词  
    ip  | 段落
    ap  |光标所在段落
    i<  |<>里面的文本
    ｉ{ |{}里面的文本
    i”  |""里面的文本
    
    ***使用mark选择:??  ***
    
    u U ~ 分别是所有字母变小写、变大写、反转大小写. 例如 gu gU g~ 
    “>”和“<" 将选中字符右移或左移 shiftwidth位置  
    
         
    使用textobj 选择:   
    i, 和 a, ：参数对象，写代码一半在修改，现在可以用   di, 或 ci, 一次性删除/改写当前参数.   
    ii 和 ai ：缩进对象，同一个缩进层次的代码，可以用 vii 选中，dii / cii 删除或改写.   
    if 和 af ：函数对象，可以用 vif / dif / cif 来选中/删除/改写函数的内容    
      
      ps: 还有 quote, usr 等选择工具...
        
        ***插入/复制*** 　　
        y{motion}?????　　　
        yy命令复制当前整行的内容到vi缓冲区.  
        yw复制当前光标所在位置到单词尾字符的内容到vi缓存区，相当于复制一个单词  
        y$复制光标所在位置到行尾内容到缓存区  
        y^复制光标所在位置到行首内容到缓存区  
#yy例如：5yy就是复制5行    
#1,#2y : 复制 #1 到#2行.  
#yw例如：2yw就是复制两个单词  
        yG   
        y1G   
        
        ***删除***      
        d0　　　　　删至行首  
        d$　　　　　删至行尾  
        D　(不可用) 删除本行光标右边的所有文字，包括光标位置的字母  
        d$　　　　　删除本行光标右边的所有文字，包括光标位置的字母  
        dw　　　　　删除光标右边的一个单词  
        ndw　　　　删除n个单词    
        d1G　　　　删除光标所在行以上的所有行  
        dG　　　　 删除光标所在行及光标以下所有行     
#d<cr> /#dd  删除# 行   
        d{motion}：和c{motion}差不多，但是不进入插入模式。   
        c{motion}：删除 motion命令跨过的字符，并且进入插入模式。比如：c$，这将会删除从光标位置到行尾的字符并且进入插入模式。ct！，这会删除从光标位置到下一个叹号（但不包括），然后进入插入模式。被删除的字符被存在了剪贴板里面，并且可以再粘贴出来。  
           　　
#x  删除#个字符   
#s 删除#个字符,进插入   
#S 删除#行, 进插入..　　
           
           ***替换***  
           r　　 替换当前字符   #r 
           R　　 替换当前字符及其后的字符，直至按ESC键. 
           
           :s/pattern1/pattern2/g　　　　把光标当前行的pattern1替换为pattern2  
           :%s/pattern1/pattern2/g　　 把所有行的pattern1替换为pattern2  
           :g/parttern1/s//parttern2　　把所有行的pattern1替换为pattern2  
           :num1"}"]}"}}" }
