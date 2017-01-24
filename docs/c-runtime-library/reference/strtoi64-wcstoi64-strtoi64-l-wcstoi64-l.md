---
title: "_strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strtoi64"
  - "_strtoi64_l"
  - "_wcstoi64_l"
  - "_wcstoi64"
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
  - "_strtoi64"
  - "strtoi64"
  - "_stroi64_l"
  - "_wcstoi64_l"
  - "wcstoi64_l"
  - "_wcstoi64"
  - "wcstoi64"
  - "strtoi64_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strtoi64 - функция"
  - "_strtoi64_l - функция"
  - "_wcstoi64 - функция"
  - "_wcstoi64_l - функция"
  - "преобразование строк, к целым числам"
  - "strtoi64 - функция"
  - "strtoi64_l - функция"
  - "wcstoi64 - функция"
  - "wcstoi64_l - функция"
ms.assetid: ea2abc50-7bfe-420e-a46b-703c3153593a
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразование строки в значение типа `__int64`.  
  
## Синтаксис  
  
```  
__int64 _strtoi64(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
__int64 _wcstoi64(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
__int64 _strtoi64_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
__int64 _wcstoi64_l(  
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
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 `_strtoi64` возвращает значение, которое представлено в строке `nptr`, кроме случаев, когда представление вызвало бы переполнение; в этом случае возвращается значение `_I64_MAX` или `_I64_MIN`.  Функция вернет 0, если преобразование не может быть выполнено.  `_wcstoi64` возвращает значения аналогично `strtoi64`.  
  
 `_I64_MAX` и `_I64_MIN` определены в LIMITS.H.  
  
 Если `nptr` имеет значение `NULL` или `base` отлично от нуля или либо меньше 2 или больше 36, то параметр `errno` получает значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_strtoi64`преобразует `nptr` в `__int64`.  Обе функции прекращают чтение строки `nptr` на первом знаке, который они не могут распознать как часть числа.  Это может быть конечный символ null или первый числовой символ, который больше или равен `base`.  `_wcstoi64` — это двухбайтовая версия `_strtoi64`; её аргумент `nptr` — строка двухбайтовых символов.  В остальном эти функции ведут себя идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcstoi64`|`_strtoi64`|`_strtoi64`|`_wcstoi64`|  
|`_tcstoi64_l`|`_strtoi64_l`|`_strtoi64_l`|`_wcstoi64_l`|  
  
 Параметр категории `LC_NUMERIC` языкового стандарта определяет распознавание символа системы счисления в `nptr`*;* дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Функции, не имеющие суффикса \_l, используют текущий языковой стандарт; `_strtoi64_l` и`_wcstoi64_l` идентичны соответствующей функции, которая не имеет суффикса `_l`, за исключением того, что они используют переданный им языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если `endptr` не равен `NULL`, то указатель на символ, из\-за которого было прекращено сканирование, хранится в ячейке памяти, на которую указывает `endptr`.  Если преобразование не может быть выполнено \(допустимые цифры не были найдены, или было указано недопустимое основание\), то значение `nptr` хранится в ячейке памяти, на которую указывает `endptr`.  
  
 `_strtoi64` ожидает, что `nptr` указывает на строку следующей формы:  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits`\]  
  
 `whitespace` может состоять из пробелов и символов табуляции, которые игнорируются. `digits` — одна или несколько десятичных цифр.  Первый символ, который не удовлетворяет этой форме, прекращает сканирование.  Если `base` от 2 до 36, то он используется как основание системы счисления.  Если значение `base` равно 0, то начальные символы строки, указанной в `nptr` используются для идентификации базы.  Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число.  Если первый символ — «0», а второй символ не равен «x» или «x», строка интерпретируется как шестнадцатеричное целое число.  Если первый символ от «1» до «9», строка интерпретируется как десятичное целое число.  Буквы от «а» до «z» присваиваются значения от 10 до 35; разрешены только буквы с присвоенными значениями меньше `base`.  Первый символ вне диапазона базы останавливает сканирование.  Например, если `base` — 0 и первый сканированный символ — "0", то предполагается восьмеричное целое число и символ "8" или "9" остановит сканирование.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_strtoi64`, `_strtoi64_l`|\<stdlib.h\>|  
|`_wcstoi64`, `_wcstoi64_l`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)