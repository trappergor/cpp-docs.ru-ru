---
title: "strtol, wcstol, _strtol_l, _wcstol_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strtol"
  - "wcstol"
  - "_strtol_l"
  - "_wcstol_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wcstol_l"
  - "strtol"
  - "_tcstol"
  - "wcstol"
  - "_strtol_l"
  - "_tcstol_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtol_l - функция"
  - "_tcstol - функция"
  - "_wcstol_l - функция"
  - "преобразование строк, к целым числам"
  - "strtol - функция"
  - "strtol_l - функция"
  - "tcstol - функция"
  - "wcstol - функция"
  - "wcstol_l - функция"
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# strtol, wcstol, _strtol_l, _wcstol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует строки в целочисленное значение типа long.  
  
## Синтаксис  
  
```  
long strtol(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
long wcstol(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
long _strtol_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
long _wcstol_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `nptr`  
 Строка, заканчивающаяся нулевым символом, для преобразования.  
  
 `endptr`  
 Указатель на символ, который останавливает сканирование.  
  
 `base`  
 Основание системы счисления, который следует использовать.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 `strtol` возвращает значение, которое представлено в строке `nptr`, кроме случаев, когда представление вызвало бы переполнение; в этом случае возвращается значение `LONG_MAX` или `LONG_MIN`.  `strtol` возвращает 0, если преобразование не может быть выполнено.  `wcstol` возвращает значения аналогично `strtol`.  Для обеих функций параметр `errno` имеет значение `ERANGE`, если переполнение или потеря точности происходит.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `strtol` преобразовывает `nptr` в `long`.  `strtol` прекращает чтение строки `nptr` на первом знаке, который она не может распознать как часть числа.  Это может быть конечный символ null или первый числовой символ, который больше или равен `base`.  
  
 `wcstol` — это двухбайтовая версия `strtol`; её аргумент `nptr` — строка двухбайтовых символов.  В остальном эти функции ведут себя идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcstol`|`strtol`|`strtol`|`wcstol`|  
|`_tcstol_l`|`_strtol_l`|`_strtol_l`|`_wcstol_l`|  
  
 Параметр категории `LC_NUMERIC` текущего языкового стандарта определяет распознавание символа системы счисления в `nptr`*;* дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Функции, не имеющие суффикса `_l`, используют текущий языковой стандарт; `_strtol_l` и `_wcstol_l` идентичны соответствующим функциям, которые не имеют суффикса `_l`, за исключением того, что они используют переданный им языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если `endptr` не равен `NULL`, то указатель на символ, из\-за которого было прекращено сканирование, хранится в ячейке памяти, на которую указывает `endptr`.  Если преобразование не может быть выполнено \(допустимые цифры не были найдены, или было указано недопустимое основание\), то значение `nptr` хранится в ячейке памяти, на которую указывает `endptr`.  
  
 `strtol` ожидает, что `nptr` указывает на строку следующей формы:  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits`\]  
  
 `whitespace` может состоять из пробелов и символов табуляции, которые игнорируются. `digits` — одна или несколько десятичных цифр.  Первый символ, который не удовлетворяет этой форме, прекращает сканирование.  Если `base` от 2 до 36, то он используется как основание системы счисления.  Если значение `base` равно 0, то начальные символы строки, указанной в `nptr` используются для идентификации базы.  Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число.  Если первый символ — «0», а второй символ не равен «x» или «x», строка интерпретируется как шестнадцатеричное целое число.  Если первый символ от «1» до «9», строка интерпретируется как десятичное целое число.  Буквы от «а» до «z» присваиваются значения от 10 до 35; разрешены только буквы с присвоенными значениями меньше `base`.  Первый символ вне диапазона базы останавливает сканирование.  Например, если `base` — 0 и первый сканированный символ — "0", то предполагается восьмеричное целое число и символ "8" или "9" остановит сканирование.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strtol`|\<stdlib.h\>|  
|`wcstol`|\<stdlib.h\> или \<wchar.h\>|  
|`_strtol_l`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
## Эквивалент в .NET Framework  
 [System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)