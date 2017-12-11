---
layout: post
title: "About Me"
date: 2017-12-11
excerpt: "Mips ve assembly kodları giriş."
tags: [sample post, readability, test]
---
**About Me**
===
Nama saya   : Yolanda Suryani
Jurusan     : Sistem Informasi 
Fakultas    : Sains dan Teknologi
Universitas : Islam Negeri Sultan Syarif Kasim Riau

Register'lar Neden Var
---
İşlemci birim zamanda sadece bir işlem yapabilir. Örneğin 3 sayıyı toplamasını istediğimizde önce ilk ikisini toplayacak, sonra ara sonucu tekrar ram'e yazacak. Sonra bu ara sonuç ile 3. sayıyı tekrar çağırıp onlarıda toplayacak. Sonra tekrar Ram'e kadar gidi yazacak. Fakat ara sonucu işlemcinin içerisinde tutabilseydik işlemleri daha hızlı gerçekleştirebilirdik. Her işlemden sonra verileri ram'e götürüp yazmak zorunda kalmazdık. Böyle diyerek işlemcinin içerisine registerları eklemişler.

Hangi Register Ne işe Yarar
---

|  Register |  Sayısı |  Açıklama |
|:---|:---:|---:|
| $zero     | 0     | İçerisinde 0 sayısı vardır.  |
|---
| $at       | 1     | Assembler tarafından kullanılır.  |
|---
| $v0-$v1  | 2-3   | Metodların return değişkenleri için. |
|---
| $a0-$a3  | 4-7   | Metodlara gidecek parametreler için. |
|---
| $t0-$t7  | 8-15  | Geçici değişkenler  |
|---
| $s0-$s7  | 16-23 | Kayıt registerları |
|---
| $t8-$t9  | 24-25 | Biraaz daha geçici değişken  |
|---
| $k0-$k1  | 26-27 | İşletim sistemi tarafından kullanılır. |
|---
| $gp      | 28    | Global Pointer  |
|---
| $sp      | 29    | Stack Pointer |
|---
| $fp      | 30    | Frame Pointer  |
|===
| $ra      | 31    | Return Adress |


Örnek Bir Assembly Kodu
---
C dilinde yazılmış `f = (a+b)+(c+d)` işlemini assembly ile yazalım.
(Değişkenler sırasıyla s0,s1,s2,s3,s4 registerlarına getirilmiştir.)
{% highlight ca65 %}
add $t0, $s1, $s2
add $t1, $s3, $s4
add $s0, $t0, $t1
{% endhighlight %}
