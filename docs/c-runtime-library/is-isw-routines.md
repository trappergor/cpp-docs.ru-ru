---
title: "Процедуры is, isw | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "isw"
  - "is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is - процедуры"
  - "isw - процедуры"
ms.assetid: 1e171a57-2cde-41f6-a75f-a080fa3c12e5
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Процедуры is, isw
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

|||  
|-|-|  
|[isalnum, iswalnum, \_isalnum\_l, \_iswalnum\_l](../Topic/isalnum,%20iswalnum,%20_isalnum_l,%20_iswalnum_l.md)|[isgraph, iswgraph, \_isgraph\_l, \_iswgraph\_l](../Topic/isgraph,%20iswgraph,%20_isgraph_l,%20_iswgraph_l.md)|  
|[isalpha, iswalpha, \_isalpha\_l, \_iswalpha\_l](../Topic/isalpha,%20iswalpha,%20_isalpha_l,%20_iswalpha_l.md)|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|  
|[isascii, \_\_isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)|[islower, iswlower, \_islower\_l, \_iswlower\_l](../Topic/islower,%20iswlower,%20_islower_l,%20_iswlower_l.md)|  
|[isblank, iswblank, \_isblank\_l, \_iswblank\_l](../c-runtime-library/reference/isblank-iswblank-isblank-l-iswblank-l.md)|[isprint, iswprint, \_isprint\_l, \_iswprint\_l](../c-runtime-library/reference/isprint-iswprint-isprint-l-iswprint-l.md)|  
|[iscntrl, iswcntrl, \_iscntrl\_l, \_iswcntrl\_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md)|[ispunct, iswpunct, \_ispunct\_l, \_iswpunct\_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md)|  
|[iscsym, iscsymf, \_\_iscsym, \_\_iswcsym, \_\_iscsymf, \_\_iswcsymf, \_iscsym\_l, \_iswcsym\_l, \_iscsymf\_l, \_iswcsymf\_l](../c-runtime-library/reference/iscsym-functions.md)|[isspace, iswspace, \_isspace\_l, \_iswspace\_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md)|  
|[\_isctype, iswctype, \_isctype\_l, \_iswctype\_l](../Topic/_isctype,%20iswctype,%20_isctype_l,%20_iswctype_l.md)|[isupper, \_isupper\_l, iswupper, \_iswupper\_l](../Topic/isupper,%20_isupper_l,%20iswupper,%20_iswupper_l.md)|  
|[isdigit, iswdigit, \_isdigit\_l, \_iswdigit\_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md)|[isxdigit, iswxdigit, \_isxdigit\_l, \_iswxdigit\_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md)|  
  
## Заметки  
 Эта процедура проверяет символы на соответствие заданным условиям.  
  
 Процедуры **is** выдают значащий результат для любого целочисленного аргумента от –1 \(`EOF`\) до **UCHAR\_MAX** \(0xFF\) включительно.  Ожидается тип аргумента `int`.  
  
> [!CAUTION]
>  Для **is** процедур передача аргумента типа `char` может привести к непредсказуемым результатам.  Однобайтовый знак типа `char` со значением, превышающем 0x7F, в однобайтовой или многобайтовой кодировке является отрицательным.  Если передается значение типа `char`, компилятор может преобразовать это значение в значение типа `int` со знаком или **long** со знаком.  Данное значение может быть расширено знаком компилятором, что приведет к непредвиденным результатам.  
  
 Процедуры **isw** выдают значащие результаты для любого целого числа от –1 \(**WEOF**\) до 0xFFFF включительно.  Тип данных **wint\_t** определяется в WCHAR.H как **unsigned short**; он может содержать любое значение расширенного символа или расширенного символа конца файла \(**WEOF**\).  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса **\_l** используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом **\_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  
  
 В языковом стандарте «C» следующие условия теста для процедуры **is**:  
  
 `isalnum`  
 Алфавитно\-цифровые символы \(a\-z, a\-z или от 0 до 9\).  
  
 `isalpha`  
 Алфавитные \(a\-z или a\-z\).  
  
 `__isascii`  
 Символы ASCII \(0x00 — 0x7F\).  
  
 `isblank`  
 Горизонтальная табуляция или пробел \(0x09 или 0x20\).  
  
 `iscntrl`  
 Управляющий символ \(0x1F или 0x00 — 0x7F\).  
  
 `__iscsym`  
 Буква, символ подчеркивания или цифра.  
  
 `__iscsymf`  
 Буква или символ подчеркивания.  
  
 **isdigit**  
 Десятичная цифра \(0 – 9\).  
  
 `isgraph`  
 Печатные символы, кроме пробела \( \).  
  
 `islower`  
 Буквы нижнего регистра \(a – z\).  
  
 `isprint`  
 Печатные символы, включая пробел \(0x20 — 0x7E\).  
  
 `ispunct`  
 Знак препинания.  
  
 `isspace`  
 Знак пробела \(0x09 — 0x0D или 0x20\).  
  
 `isupper`  
 Буквы верхнего регистра \(A – Z\).  
  
 `isxdigit`  
 Шестнадцатеричная цифра \(А — F, a — f или 0 — 9\).  
  
 Для процедуры **isw**, результаты теста для заданного условия не зависят от языкового стандарта.  Условия теста для функций **isw** следующие:  
  
 `iswalnum`  
 `iswalpha` или `iswdigit`.  
  
 `iswalpha`  
 Любой расширенный символ из набора, определенного реализацией, для которого ни одно из `iswcntrl`, `iswdigit`, `iswpunct` или `iswspace` отлично от нуля.  `iswalpha` возвращает ненулевое значение только для расширенных символов, для которых  `iswupper` или `iswlower` ненулевые.  
  
 `iswascii`  
 Представление символа ASCII \(0x0000 — 0x007F\) в расширенных символах.  
  
 `iswblank`  
 Расширенный символ, соответствующий стандартному пробелу или являющийся одним из определенных реализацией символов, для которых `iswalnum` ложно.  Стандартные пустые символы представляют собой пробел \(L' '\) и символ горизонтальной табуляции \(L'\\t'\).  
  
 `iswcntrl`  
 Расширенный символ управления.  
  
 **\_\_iswcsym**  
 Любой расширенный символ, для которого **isalnum**  имеет значение true, или символ '\_'.  
  
 **\_\_iswcsymf**  
 Любой расширенный символ, для которого `iswalpha` имеет значение true, или символ '\_'.  
  
 `iswctype`  
 Символ содержит значение свойства, указанного аргументом `desc`.  Для каждого допустимого значения аргумента `desc` `iswctype`, существует эквивалентная функция, работающая с расширенными символами, как показано в следующей таблице:  
  
 **Эквивалентность iswctype \(**   
 ***c, desc* \) другим процедурам тестирования isw**  
  
|Значение аргумента *desc*|эквивалент iswctype\( *c, desc* \)|  
|-------------------------------|----------------------------------------|  
|**\_ALPHA**|**iswalpha\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_DIGIT**|**iswalnum\(** `c` **\)**|  
|**\_BLANK**|**iswblank\(** `c` **\)**|  
|**\_CONTROL**|**iswcntrl\(** `c` **\)**|  
|**\_DIGIT**|**iswdigit\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_DIGIT** &#124; **\_PUNCT**|**iswgraph\(** `c` **\)**|  
|**\_LOWER**|**iswlower\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_BLANK** &#124; **\_DIGIT** &#124; **\_PUNCT**|**iswprint\(** `c` **\)**|  
|**\_PUNCT**|**iswpunct\(** `c` **\)**|  
|**\_BLANK**|**iswblank\(** `c` **\)**|  
|**\_SPACE**|**iswspace\(** `c` **\)**|  
|**\_UPPER**|**iswupper\(** `c` **\)**|  
|**\_HEX**|**iswxdigit\(** `c` **\)**|  
  
 `iswdigit`  
 Расширенный символ, соответствующий символу десятичной цифры  
  
 `iswgraph`  
 Печатные расширенные символы, кроме расширенного символа пробела \(L' '\).  
  
 `iswlower`  
 Строчная буква или член определенного реализацией набора расширенных символов, для которых ни одно из `iswcntrl`, `iswdigit`, `iswpunct` или `iswspace` отлично от нуля.  `iswlower` возвращает ненулевое значение только для расширенных символов, которые соответствуют буквам нижнего регистра.  
  
 `iswprint`  
 Печатные расширенные символы, включая расширенный символа пробела \(L' '\).  
  
 `iswpunct`  
 Печатные расширенные символы, которые не являются ни расширенным символом пробела \(L' '\), ни расширенным символом, для которого `iswalnum` отлично от нуля.  
  
 `iswspace`  
 Расширенный символ, соответствующий стандартному пробелу или являющийся одним из определенных реализацией символов, для которых `iswalnum` ложно.  Стандартные пробельные символы: пробел \(L' '\), символ конца страницы \(L'\\f'\), символ новой строки \(L'\\n'\), символ возврата каретки \(L'\\r'\), символ горизонтальной табуляции \(L'\\t'\), символ вертикальной табуляции \(L'\\v'\).  
  
 `iswupper`  
 Расширенный символ верхнего регистра или один из набора определенных реализацией расширенных символов, для которых ни одно из `iswcntrl`, `iswdigit`, `iswpunct` или `iswspace` не равно нулю.  `iswupper` возвращает ненулевое значение только для расширенных символов, которые соответствуют буквам верхнего регистра.  
  
 `iswxdigit`  
 Расширенный символ, который соответствует символу шестнадцатеричной цифры.  
  
## Пример  
  
```  
// crt_isfam.c  
/* This program tests all characters between 0x0  
 * and 0x7F, then displays each character with abbreviations  
 * for the character-type codes that apply.  
 */  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   for( ch = 0; ch <= 0x7F; ch++ )  
   {  
      printf( "%.2x  ", ch );  
      printf( " %c", isprint( ch )  ? ch   : ' ' );  
      printf( "%4s", isalnum( ch )  ? "AN" : "" );  
      printf( "%3s", isalpha( ch )  ? "A"  : "" );  
      printf( "%3s", __isascii( ch )  ? "AS" : "" );  
      printf( "%3s", iscntrl( ch )  ? "C"  : "" );  
      printf( "%3s", __iscsym( ch )  ? "CS "  : "" );  
      printf( "%3s", __iscsymf( ch )  ? "CSF"  : "" );  
      printf( "%3s", isdigit( ch )  ? "D"  : "" );  
      printf( "%3s", isgraph( ch )  ? "G"  : "" );  
      printf( "%3s", islower( ch )  ? "L"  : "" );  
      printf( "%3s", ispunct( ch )  ? "PU" : "" );  
      printf( "%3s", isspace( ch )  ? "S"  : "" );  
      printf( "%3s", isprint( ch )  ? "PR" : "" );  
      printf( "%3s", isupper( ch )  ? "U"  : "" );  
      printf( "%3s", isxdigit( ch ) ? "X"  : "" );  
      printf( ".\n" );  
   }  
}  
```  
  
## Output  
  
```  
00            AS  C                              .  
01            AS  C                              .  
02            AS  C                              .  
03            AS  C                              .  
04            AS  C                              .  
05            AS  C                              .  
06            AS  C                              .  
07            AS  C                              .  
08            AS  C                              .  
09            AS  C                    S         .  
0a            AS  C                    S         .  
0b            AS  C                    S         .  
0c            AS  C                    S         .  
0d            AS  C                    S         .  
0e            AS  C                              .  
0f            AS  C                              .  
10            AS  C                              .  
11            AS  C                              .  
12            AS  C                              .  
13            AS  C                              .  
14            AS  C                              .  
15            AS  C                              .  
16            AS  C                              .  
17            AS  C                              .  
18            AS  C                              .  
19            AS  C                              .  
1a            AS  C                              .  
1b            AS  C                              .  
1c            AS  C                              .  
1d            AS  C                              .  
1e            AS  C                              .  
1f            AS  C                              .  
20            AS                       S PR      .  
21   !        AS              G    PU    PR      .  
22   "        AS              G    PU    PR      .  
23   #        AS              G    PU    PR      .  
24   $        AS              G    PU    PR      .  
25   %        AS              G    PU    PR      .  
26   &        AS              G    PU    PR      .  
27   '        AS              G    PU    PR      .  
28   (        AS              G    PU    PR      .  
29   )        AS              G    PU    PR      .  
2a   *        AS              G    PU    PR      .  
2b   +        AS              G    PU    PR      .  
2c   ,        AS              G    PU    PR      .  
2d   -        AS              G    PU    PR      .  
2e   .        AS              G    PU    PR      .  
2f   /        AS              G    PU    PR      .  
30   0  AN    AS   CS      D  G          PR     X.  
31   1  AN    AS   CS      D  G          PR     X.  
32   2  AN    AS   CS      D  G          PR     X.  
33   3  AN    AS   CS      D  G          PR     X.  
34   4  AN    AS   CS      D  G          PR     X.  
35   5  AN    AS   CS      D  G          PR     X.  
36   6  AN    AS   CS      D  G          PR     X.  
37   7  AN    AS   CS      D  G          PR     X.  
38   8  AN    AS   CS      D  G          PR     X.  
39   9  AN    AS   CS      D  G          PR     X.  
3a   :        AS              G    PU    PR      .  
3b   ;        AS              G    PU    PR      .  
3c   <        AS              G    PU    PR      .  
3d   =        AS              G    PU    PR      .  
3e   >        AS              G    PU    PR      .  
3f   ?        AS              G    PU    PR      .  
40   @        AS              G    PU    PR      .  
41   A  AN  A AS   CS CSF     G          PR  U  X.  
42   B  AN  A AS   CS CSF     G          PR  U  X.  
43   C  AN  A AS   CS CSF     G          PR  U  X.  
44   D  AN  A AS   CS CSF     G          PR  U  X.  
45   E  AN  A AS   CS CSF     G          PR  U  X.  
46   F  AN  A AS   CS CSF     G          PR  U  X.  
47   G  AN  A AS   CS CSF     G          PR  U   .  
48   H  AN  A AS   CS CSF     G          PR  U   .  
49   I  AN  A AS   CS CSF     G          PR  U   .  
4a   J  AN  A AS   CS CSF     G          PR  U   .  
4b   K  AN  A AS   CS CSF     G          PR  U   .  
4c   L  AN  A AS   CS CSF     G          PR  U   .  
4d   M  AN  A AS   CS CSF     G          PR  U   .  
4e   N  AN  A AS   CS CSF     G          PR  U   .  
4f   O  AN  A AS   CS CSF     G          PR  U   .  
50   P  AN  A AS   CS CSF     G          PR  U   .  
51   Q  AN  A AS   CS CSF     G          PR  U   .  
52   R  AN  A AS   CS CSF     G          PR  U   .  
53   S  AN  A AS   CS CSF     G          PR  U   .  
54   T  AN  A AS   CS CSF     G          PR  U   .  
55   U  AN  A AS   CS CSF     G          PR  U   .  
56   V  AN  A AS   CS CSF     G          PR  U   .  
57   W  AN  A AS   CS CSF     G          PR  U   .  
58   X  AN  A AS   CS CSF     G          PR  U   .  
59   Y  AN  A AS   CS CSF     G          PR  U   .  
5a   Z  AN  A AS   CS CSF     G          PR  U   .  
5b   [        AS              G    PU    PR      .  
5c   \        AS              G    PU    PR      .  
5d   ]        AS              G    PU    PR      .  
5e   ^        AS              G    PU    PR      .  
5f   _        AS   CS CSF     G    PU    PR      .  
60   `        AS              G    PU    PR      .  
61   a  AN  A AS   CS CSF     G  L       PR     X.  
62   b  AN  A AS   CS CSF     G  L       PR     X.  
63   c  AN  A AS   CS CSF     G  L       PR     X.  
64   d  AN  A AS   CS CSF     G  L       PR     X.  
65   e  AN  A AS   CS CSF     G  L       PR     X.  
66   f  AN  A AS   CS CSF     G  L       PR     X.  
67   g  AN  A AS   CS CSF     G  L       PR      .  
68   h  AN  A AS   CS CSF     G  L       PR      .  
69   i  AN  A AS   CS CSF     G  L       PR      .  
6a   j  AN  A AS   CS CSF     G  L       PR      .  
6b   k  AN  A AS   CS CSF     G  L       PR      .  
6c   l  AN  A AS   CS CSF     G  L       PR      .  
6d   m  AN  A AS   CS CSF     G  L       PR      .  
6e   n  AN  A AS   CS CSF     G  L       PR      .  
6f   o  AN  A AS   CS CSF     G  L       PR      .  
70   p  AN  A AS   CS CSF     G  L       PR      .  
71   q  AN  A AS   CS CSF     G  L       PR      .  
72   r  AN  A AS   CS CSF     G  L       PR      .  
73   s  AN  A AS   CS CSF     G  L       PR      .  
74   t  AN  A AS   CS CSF     G  L       PR      .  
75   u  AN  A AS   CS CSF     G  L       PR      .  
76   v  AN  A AS   CS CSF     G  L       PR      .  
77   w  AN  A AS   CS CSF     G  L       PR      .  
78   x  AN  A AS   CS CSF     G  L       PR      .  
79   y  AN  A AS   CS CSF     G  L       PR      .  
7a   z  AN  A AS   CS CSF     G  L       PR      .  
7b   {        AS              G    PU    PR      .  
7c   |        AS              G    PU    PR      .  
7d   }        AS              G    PU    PR      .  
7e   ~        AS              G    PU    PR      .  
7f            AS  C                              .  
```  
  
## См. также  
 [Классификация символов](../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../c-runtime-library/locale.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Функции to](../c-runtime-library/to-functions.md)