---
title: "strtoul, _strtoul_l, wcstoul, _wcstoul_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcstoul_l"
  - "_strtoul_l"
  - "strtoul"
  - "wcstoul"
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
  - "strtoul"
  - "_tcstoul"
  - "wcstoul"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoul_l - функция"
  - "_tcstoul - функция"
  - "_wcstoul_l - функция"
  - "преобразование строк, к целым числам"
  - "strtoul - функция"
  - "strtoul_l - функция"
  - "tcstoul - функция"
  - "wcstoul - функция"
  - "wcstoul_l - функция"
ms.assetid: 38f2afe8-8178-4e0b-8bbe-d5c6ad66e3ab
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# strtoul, _strtoul_l, wcstoul, _wcstoul_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует строки в длинное целое без знака.  
  
## Синтаксис  
  
```  
unsigned long strtoul(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned long _strtoul_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned long wcstoul(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned long _wcstoul_l(  
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
 `strtoul` возвращает преобразованное значение, если оно есть, или `ULONG_MAX` при переполнении.  `strtoul` возвращает 0, если преобразование не может быть выполнено.  `wcstoul` возвращает значения аналогично `strtoul`.  Для обеих функций параметр `errno` имеет значение `ERANGE`, если переполнение или потеря точности происходит.  
  
 См. раздел [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для дополнительных сведений по этим и другим кодам возврата.  
  
## Заметки  
 Каждая из этих функций преобразует входную строку `nptr` в значение `unsigned` `long`.  
  
 `strtoul` прекращает чтение строки `nptr` на первом знаке, который она не может распознать как часть числа.  Это может быть конечный символ null или первый числовой символ, который больше или равен `base`.  Категория `LC_NUMERIC` задает настройки языкового стандарта определяет распознавание символа системы счисления в `nptr`; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  `strtoul` и  `wcstoul` используют текущий языковой стандарт; `_strtoul_l` и  `_wcstoul_l` идентичны им за исключением того, что используют вместо него переданный языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если `endptr` не равен `NULL`, то указатель на символ, из\-за которого было прекращено сканирование, хранится в ячейке памяти, на которую указывает `endptr`.  Если преобразование не может быть выполнено \(допустимые цифры не были найдены, или было указано недопустимое основание\), то значение `nptr` хранится в ячейке памяти, на которую указывает `endptr`.  
  
 `wcstoul` — это двухбайтовая версия `strtoul`; её аргумент `nptr` — строка двухбайтовых символов.  В противном случае эти функции ведут себя идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcstoul`|`strtoul`|`strtoul`|`wcstoul`|  
|`_tcstoul_l`|`strtoul_l`|`_strtoul_l`|`_wcstoul_l`|  
  
 `strtoul` ожидает, что `nptr` указывает на строку следующей формы:  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits`\]  
  
 `whitespace` может состоять из пробелов и символов табуляции, которые игнорируются. `digits` — одна или несколько десятичных цифр.  Первый символ, который не удовлетворяет этой форме, прекращает сканирование.  Если `base` от 2 до 36, то он используется как основание системы счисления.  Если значение `base` равно 0, то начальные символы строки, указанной в `nptr` используются для идентификации базы.  Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число.  Если первый символ — «0», а второй символ не равен «x» или «x», строка интерпретируется как шестнадцатеричное целое число.  Если первый символ от «1» до «9», строка интерпретируется как десятичное целое число.  Буквы от «а» до «z» присваиваются значения от 10 до 35; разрешены только буквы с присвоенными значениями меньше `base`.  Первый символ вне диапазона базы останавливает сканирование.  Например, если `base` — 0 и первый сканированный символ — "0", то предполагается восьмеричное целое число и символ "8" или "9" остановит сканирование.  `strtoul` допускает в качестве префикса знак плюса \(`+`\) или знак минуса \(`–`\); знак минуса впереди показывает, что возвращаемое значение отрицается.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strtoul`|\<stdlib.h\>|  
|`wcstoul`|\<stdlib.h\> или \<wchar.h\>|  
|`_strtoul_l`|\<stdlib.h\>|  
|`_wcstoul_l`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
## Эквивалент в .NET Framework  
 [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)