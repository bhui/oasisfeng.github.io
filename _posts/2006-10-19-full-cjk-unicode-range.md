---
id: 136
title: 完整的CJK Unicode范围（5.0版）
date: 2006-10-19T00:05:04+00:00
author: oasisfeng
layout: post
guid: http://blog.oasisfeng.com/2006/10/19/full-cjk-unicode-range/
permalink: /2006/10/19/full-cjk-unicode-range/
dsq_thread_id:
  - "250426443"
  - "250426443"
categories:
  - Development
  - Software
tags:
  - CJK
  - Unicode
---
　　因为FontRouter新版本开发的需要，在网上搜索了一下汉字的Unicode范围，普遍给出了“U+4E00..U+9FA5”。但事实上这个范围是不完整的，甚至连基本的全角（中文）标点也未包含在内。为此，我特地查询了Unicode官方的Code Charts数据库，并根据最新的Unicode 5.0版整理如下：

**注：在绝大多数应用场合中，我们可以仅用（1）、（2）、（3）、（4）、（5）的集合作为CJK判断的依据。**

<!--more-->1）标准CJK文字


  
http://www.unicode.org/Public/UNIDATA/Unihan.html

<table border="1" bordercolor="#cccccc" cellpadding="0" cellspacing="0">
  <tr>
    <th>
      Code point range
    </th>
    
    <th>
      Block name
    </th>
    
    <th>
      Release
    </th>
  </tr>
  
  <tr>
    <td>
      U+3400..U+4DB5
    </td>
    
    <td>
      CJK Unified Ideographs Extension A
    </td>
    
    <td>
      3.0
    </td>
  </tr>
  
  <tr>
    <td>
      U+4E00..U+9FA5
    </td>
    
    <td>
      CJK Unified Ideographs
    </td>
    
    <td>
      1.1
    </td>
  </tr>
  
  <tr>
    <td>
      U+9FA6..U+9FBB
    </td>
    
    <td>
      CJK Unified Ideographs
    </td>
    
    <td>
      4.1
    </td>
  </tr>
  
  <tr>
    <td>
      U+F900..U+FA2D
    </td>
    
    <td>
      CJK Compatibility Ideographs
    </td>
    
    <td>
      1.1
    </td>
  </tr>
  
  <tr>
    <td>
      U+FA30..U+FA6A
    </td>
    
    <td>
      CJK Compatibility Ideographs
    </td>
    
    <td>
      3.2
    </td>
  </tr>
  
  <tr>
    <td>
      U+FA70..U+FAD9
    </td>
    
    <td>
      CJK Compatibility Ideographs
    </td>
    
    <td>
      4.1
    </td>
  </tr>
  
  <tr>
    <td>
      U+20000..U+2A6D6
    </td>
    
    <td>
      CJK Unified Ideographs Extension B
    </td>
    
    <td>
      3.1
    </td>
  </tr>
  
  <tr>
    <td>
      U+2F800..U+2FA1D
    </td>
    
    <td>
      CJK Compatibility Supplement
    </td>
    
    <td>
      3.1
    </td>
  </tr>
</table>

2）全角ASCII、全角中英文标点、半宽片假名、半宽平假名、半宽韩文字母：FF00-FFEF
  
http://www.unicode.org/charts/PDF/UFF00.pdf

3）CJK部首补充：2E80-2EFF
  
http://www.unicode.org/charts/PDF/U2E80.pdf

4）CJK标点符号：3000-303F
  
http://www.unicode.org/charts/PDF/U3000.pdf

5）CJK笔划：31C0-31EF
  
http://www.unicode.org/charts/PDF/U31C0.pdf

6）康熙部首：2F00-2FDF
  
http://www.unicode.org/charts/PDF/U2F00.pdf

7）汉字结构描述字符：2FF0-2FFF
  
http://www.unicode.org/charts/PDF/U2FF0.pdf

8）注音符号：3100-312F
  
http://www.unicode.org/charts/PDF/U3100.pdf

9）注音符号（闽南语、客家语扩展）：31A0-31BF
  
http://www.unicode.org/charts/PDF/U31A0.pdf

10）日文平假名：3040-309F
  
http://www.unicode.org/charts/PDF/U3040.pdf

11）日文片假名：30A0-30FF
  
http://www.unicode.org/charts/PDF/U30A0.pdf

12）日文片假名拼音扩展：31F0-31FF
  
http://www.unicode.org/charts/PDF/U31F0.pdf

13）韩文拼音：AC00-D7AF
  
http://www.unicode.org/charts/PDF/UAC00.pdf

14）韩文字母：1100-11FF
  
http://www.unicode.org/charts/PDF/U1100.pdf

15）韩文兼容字母：3130-318F
  
http://www.unicode.org/charts/PDF/U3130.pdf

16）太玄经符号：1D300-1D35F
  
http://www.unicode.org/charts/PDF/U1D300.pdf

17）易经六十四卦象：4DC0-4DFF
  
http://www.unicode.org/charts/PDF/U4DC0.pdf

18）彝文音节：A000-A48F
  
http://www.unicode.org/charts/PDF/UA000.pdf

19）彝文部首：A490-A4CF
  
http://www.unicode.org/charts/PDF/UA490.pdf

20）盲文符号：2800-28FF
  
http://www.unicode.org/charts/PDF/U2800.pdf

21）CJK字母及月份：3200-32FF
  
http://www.unicode.org/charts/PDF/U3200.pdf

22）CJK特殊符号（日期合并）：3300-33FF
  
http://www.unicode.org/charts/PDF/U3300.pdf

23）装饰符号（非CJK专用）：2700-27BF
  
http://www.unicode.org/charts/PDF/U2700.pdf

24）杂项符号（非CJK专用）：2600-26FF
  
http://www.unicode.org/charts/PDF/U2600.pdf

25）中文竖排标点：FE10-FE1F
  
http://www.unicode.org/charts/PDF/UFE10.pdf

26）CJK兼容符号（竖排变体、下划线、顿号）：FE30-FE4F
  
http://www.unicode.org/charts/PDF/UFE30.pdf

以上翻译自Unicode官方网站，部分译法可能不够准确，还望大家予以指正！如有疏漏、错误之处也请一并指出，多谢！