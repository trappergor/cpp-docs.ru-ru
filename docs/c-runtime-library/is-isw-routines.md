---
title: "Процедуры is, isw | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- isw
- is
dev_langs:
- C++
helpviewer_keywords:
- is routines
- isw routines
ms.assetid: 1e171a57-2cde-41f6-a75f-a080fa3c12e5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa1cc76bf925a334b78e5f15565c089081cfe9d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="is-isw-routines"></a>Процедуры is, isw
|||  
|-|-|  
|[isalnum, iswalnum, _isalnum_l, _iswalnum_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md)|[isgraph, iswgraph, _isgraph_l, _iswgraph_l](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md)|  
|[isalpha, iswalpha, _isalpha_l, _iswalpha_l](../c-runtime-library/reference/isalpha-iswalpha-isalpha-l-iswalpha-l.md)|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|  
|[isascii, __isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)|[islower, iswlower, _islower_l, _iswlower_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md)|  
|[isblank, iswblank, _isblank_l, _iswblank_l](../c-runtime-library/reference/isblank-iswblank-isblank-l-iswblank-l.md)|[isprint, iswprint, _isprint_l, _iswprint_l](../c-runtime-library/reference/isprint-iswprint-isprint-l-iswprint-l.md)|  
|[iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md)|[ispunct, iswpunct, _ispunct_l, _iswpunct_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md)|  
|[iscsym, iscsymf, __iscsym, \__iswcsym, \__iscsymf, \__iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l](../c-runtime-library/reference/iscsym-functions.md)|[isspace, iswspace, _isspace_l, _iswspace_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md)|  
|[_isctype, iswctype, _isctype_l, _iswctype_l](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|[isupper, _isupper_l, iswupper, _iswupper_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md)|  
|[isdigit, iswdigit, _isdigit_l, _iswdigit_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md)|[isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md)|  
  
## <a name="remarks"></a>Примечания  
 Эти подпрограммы проверяют символы на соответствие заданным условиям.  
  
 Подпрограммы **is** выдают значащий результат для любого целочисленного аргумента от –1 (`EOF`) до **UCHAR_MAX** (0xFF) включительно. Ожидается тип аргумента `int`.  
  
> [!CAUTION]
>  Для подпрограмм **is** передача аргумента типа `char` может привести к непредсказуемым результатам. Однобайтовый символ типа `char` со значением, превышающем 0x7F, в однобайтовой или многобайтовой кодировке является отрицательным. Если передается значение типа `char`, компилятор может преобразовать это значение в значение типа `int` со знаком или **long** со знаком. Компилятор может расширить знак данного значения, что приведет к непредвиденным результатам.  
  
 Подпрограммы **isw** выдают значащие результаты для любого целого числа от –1 (**WEOF**) до 0xFFFF включительно. Тип данных **wint_t** определяется в WCHAR.H как **unsigned short**; он может содержать любое значение расширенного символа или расширенный символ конца файла (**WEOF**).  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  
  
 В языковом стандарте "C" для подпрограмм **is** определены следующие условия проверки:  
  
 `isalnum`  
 Алфавитно-цифровые символы (A–Z, a–z или 0–9).  
  
 `isalpha`  
 Алфавитные (A–Z или a–z).  
  
 `__isascii`  
 Символы ASCII (0x00–0x7F).  
  
 `isblank`  
 Горизонтальная табуляция или пробел (0x09 или 0x20).  
  
 `iscntrl`  
 Управляющий символ (0x00–0x1F или 0x7F).  
  
 `__iscsym`  
 Буква, символ подчеркивания или цифра.  
  
 `__iscsymf`  
 Буква или символ подчеркивания.  
  
 **isdigit**  
 Десятичная цифра (0–9).  
  
 `isgraph`  
 Печатные символы, кроме пробела ( ).  
  
 `islower`  
 Буквы нижнего регистра (a–z).  
  
 `isprint`  
 Печатные символы, включая пробел (0x20–0x7E).  
  
 `ispunct`  
 Знак препинания.  
  
 `isspace`  
 Пробельный символ (0x09–0x0D или 0x20).  
  
 `isupper`  
 Буквы верхнего регистра (A–Z).  
  
 `isxdigit`  
 Шестнадцатеричная цифра (А–F, a–f или 0–9).  
  
 Для подпрограмм **isw** результаты проверки заданного условия не зависят от языкового стандарта. Условия проверки для функций **isw** следующие:  
  
 `iswalnum`  
 `iswalpha` или `iswdigit`.  
  
 `iswalpha`  
 Любой расширенный символ из набора, определенного реализацией, для которого ни одна из функций `iswcntrl`, `iswdigit`, `iswpunct` и `iswspace` не принимает значение, отличное от нуля. `iswalpha` возвращает ненулевое значение только для расширенных символов, для которых `iswupper` или `iswlower` имеет ненулевое значение.  
  
 `iswascii`  
 Представление символа ASCII (0x0000–0x007F) в расширенных символах.  
  
 `iswblank`  
 Расширенный символ, соответствующий стандартному пробелу или входящий в определяемый реализацией набор расширенных символов, для которых функция `iswalnum` имеет значение false. Стандартные пробельные символы — это пробел (L" ") и символ горизонтальной табуляции (L"\t").  
  
 `iswcntrl`  
 Расширенный символ управления.  
  
 **__iswcsym**  
 Любой расширенный символ, для которого функция **isalnum** имеет значение true, или символ "_".  
  
 **__iswcsymf**  
 Любой расширенный символ, для которого функция `iswalpha` имеет значение true, или символ "_".  
  
 `iswctype`  
 Символ имеет свойство, указанное аргументом `desc`. Для каждого допустимого значения аргумента `desc` функции `iswctype` существует эквивалентная функция, работающая с расширенными символами, как показано в следующей таблице:  
  
 **Эквивалентность iswctype(**   
 ***c, desc*) другим подпрограммам проверки isw**  
  
|Значение аргумента *desc*|эквивалент iswctype(*c, desc*)|  
|------------------------------|----------------------------------------|  
|**_ALPHA**|**iswalpha(** `c` **)**|  
|**_ALPHA** &#124; **_DIGIT**|**iswalnum(** `c` **)**|  
|**_BLANK**|**iswblank(** `c` **)**|  
|**_CONTROL**|**iswcntrl(** `c` **)**|  
|**_DIGIT**|**iswdigit(** `c` **)**|  
|**_ALPHA** &#124; **_DIGIT** &#124; **_PUNCT**|**iswgraph(** `c` **)**|  
|**_LOWER**|**iswlower(** `c` **)**|  
|**_ALPHA** &#124; **_BLANK** &#124; **_DIGIT** &#124; **_PUNCT**|**iswprint(** `c` **)**|  
|**_PUNCT**|**iswpunct(** `c` **)**|  
|**_BLANK**|**iswblank(** `c` **)**|  
|**_SPACE**|**iswspace(** `c` **)**|  
|**_UPPER**|**iswupper(** `c` **)**|  
|**_HEX**|**iswxdigit(** `c` **)**|  
  
 `iswdigit`  
 Расширенный символ, соответствующий символу десятичной цифры.  
  
 `iswgraph`  
 Печатный расширенный символ, кроме расширенного символа пробела (L" ").  
  
 `iswlower`  
 Строчная буква или член определенного реализацией набора расширенных символов, для которых ни одна из функций `iswcntrl`, `iswdigit`, `iswpunct` и `iswspace` не имеет значения, отличного от нуля. `iswlower` возвращает ненулевое значение только для расширенных символов, которые соответствуют буквам нижнего регистра.  
  
 `iswprint`  
 Печатный расширенный символ, включая расширенный символа пробела (L" ").  
  
 `iswpunct`  
 Печатный расширенный символ, который не является ни расширенным символом пробела (L" "), ни расширенным символом, для которого значение функции `iswalnum` отлично от нуля.  
  
 `iswspace`  
 Расширенный символ, соответствующий стандартному расширенному символу пробела или являющийся одним из определяемых реализацией расширенных символов, для которых функция `iswalnum` имеет значение false. Стандартные пробельные символы: пробел (L" "), символ конца страницы (L"\f"), символ новой строки (L"\n"), символ возврата каретки (L"\r"), символ горизонтальной табуляции (L"\t"), символ вертикальной табуляции (L"\v").  
  
 `iswupper`  
 Расширенный символ верхнего регистра или символ из набора определенных реализацией расширенных символов, для которых ни одна из функций `iswcntrl`, `iswdigit`, `iswpunct` и `iswspace` не имеет нулевого значения. Функция `iswupper` возвращает ненулевое значение только для расширенных символов, которые соответствуют буквам верхнего регистра.  
  
 `iswxdigit`  
 Расширенный символ, который соответствует символу шестнадцатеричной цифры.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="output"></a>Вывод  
  
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
  
## <a name="see-also"></a>См. также  
 [Классификация символов](../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../c-runtime-library/locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Интерпретация последовательностей многобайтовых символов](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Функции to](../c-runtime-library/to-functions.md)