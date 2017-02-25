---
title: "Позиционные параметры printf_p | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_p - функция, позиционные параметры"
  - "printf_p - функция, позиционные параметры"
ms.assetid: beb4fd85-a7aa-4665-9085-2c907a5b9ab0
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Позиционные параметры printf_p
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Позиционные параметры предоставляют возможность определить число аргументов, которые будут заменены в поле в строке формата.  Доступны следующие функции `printf` с позиционными параметрами:  
  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)  
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)  
  
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)  
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)  
  
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)  
 [\_cprintf\_p, \_cprintf\_p\_l, \_cwprintf\_p, \_cwprintf\_p\_l](../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)  
  
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)  
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)  
  
 [vprintf, \_vprintf\_l, vwprintf, \_vwprintf\_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
 [\_vprintf\_p, \_vprintf\_p\_l, \_vwprintf\_p, \_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)  
  
 [vfprintf, \_vfprintf\_l, vfwprintf, \_vfwprintf\_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)  
 [\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)  
  
 [vsprintf, \_vsprintf\_l, vswprintf, \_vswprintf\_l, \_\_vswprintf\_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)  
 [\_vsprintf\_p, \_vsprintf\_p\_l, \_vswprintf\_p, \_vswprintf\_p\_l](../Topic/_vsprintf_p,%20_vsprintf_p_l,%20_vswprintf_p,%20_vswprintf_p_l.md)  
  
## Определение позиционных параметров  
  
##### Индексирование параметров  
 По умолчанию поведение позиционных функций совпадает с поведением непозиционных, если позиционное форматирование отсутствует.  Позиционные параметры задаются в формате "`%m$x`", где `m` обозначает порядковый номер, указывающий позицию параметра в списке параметров, предшествующих строке формата, а `x` обозначает тип символа поля для типа, указанного в функции `printf`.  Параметры в списке индексируются, начиная со значения 1 для первого элемента в списке и т. д.  Дополнительные сведения о символах поля типа см. в разделе [Символы поля типа printf](../c-runtime-library/printf-type-field-characters.md).  
  
 Пример такого поведения:  
  
```  
_printf_p("%1$s %2$s", "November", "10");  
```  
  
 напечатает  
  
```  
November 10  
```  
  
 Порядок используемых чисел не совпадает с порядком, в котором даны аргументы.  Таким образом, следующее выражение допустимо:  
  
```  
_printf_p("%2$s %1$s", "November", "10");  
```  
  
 напечатает  
  
```  
10 November  
```  
  
 Параметр может использоваться более одного раза при форматировании в отличие от обычных строк формата, поэтому  
  
```  
_printf_p("%1$d times %1$d is %2$d", 10, 100);  
```  
  
 напечатает  
  
```  
10 times 10 is 100  
```  
  
 Однако все аргументы в строке формата должны использоваться по меньшей мере один раз.  
  
 Максимальное число разрешенных позиционных параметров в строке формата задается `_ARGMAX`.  
  
##### Ширина и точность  
 Если символ \* используется для указания того, что ширина или точность должны определяться из аргумента, позиция ширины или значение точности должны следовать сразу после символа \*.  Например:  
  
```  
_printf_p("%1$*2$s","Hello", 10);  
```  
  
 или  
  
```  
_printf_p("%2$*1$s",10, "Hello");  
```  
  
##### Смешивание позиционных и непозиционных аргументов  
 Позиционные параметры не могут смешиваться с непозиционными параметрами в одной строке формата.  Однако `printf_p` и связанные функции еще поддерживают непозиционные параметры в строке формата, не содержащей позиционных параметров.  
  
## Пример  
  
```  
// positional_args.c  
// Positional arguments allow the specification of the order  
// in which arguments are consumed in a formatting string.  
  
#include <stdio.h>  
  
int main(int argc, char *argv[])  
{  
    int     i = 1,  
            j = 2,  
            k = 3;  
    double  x = 0.1,  
            y = 0.2,  
            z = 0.3;  
    char    *s1 = "abc",  
            *s2 = "def",  
            *s3 = "ghi";  
  
    // If positional arguments are unspecified,  
    // normal input order is used.  
    _printf_p("%d %d %d\n", i, j, k);  
  
    // Positional args are numbers indicating the  
    // argument enclosed in curly braces.  
    _printf_p("%3$d %1$d %2$d\n", i, j, k);  
  
    // The same positional argument may be reused.  
    _printf_p("%1$d %2$d %1$d\n", i, j);  
  
    _printf_p("%1$s %2$s %3$s\n", s1, s2, s3);  
  
    _printf_p("%3$s %1$s %2$s\n", s1, s2, s3);  
}  
```  
  
  **1 2 3**  
**3 1 2**  
**1 2 1**  
**abc def ghi**  
**ghi abc def**   
## См. также  
 [Символы поля типа printf](../c-runtime-library/printf-type-field-characters.md)   
 [Спецификация ширины printf](../c-runtime-library/printf-width-specification.md)   
 [Спецификация точности](../c-runtime-library/precision-specification.md)