---
title: "strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcstoimax"
  - "_wcstoimax_l"
  - "_strtoimax_l"
  - "strtoimax"
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
  - "wcstoimax"
  - "_tcstoimax"
  - "strtoimax"
  - "_wcstoimax_l"
  - "_strtoimax_l"
  - "_tcstoimax_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoimax_l - функция"
  - "_wcstoimax_l - функция"
  - "функции преобразования"
  - "strtoimax - функция"
  - "wcstoimax - функция"
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразование строки в целочисленное значение наибольшего поддерживаемого типа целого числа со знаком.  
  
## Синтаксис  
  
```  
intmax_t strtoimax(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
intmax_t wcstoimax(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
intmax_t _strtoimax_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
intmax_t _wcstoimax_l(  
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
 `strtoimax` возвращает значение, которое представлено в строке `nptr`, кроме случаев, когда представление вызвало бы переполнение — в этом случае возвращается значение `INTMAX_MAX` или `INTMAX_MIN`, а `errno` имеет значение `ERANGE`.  Функция возвращает 0, если преобразование не может быть выполнено.  `wcstoimax` возвращает значения аналогично `strtoimax`.  
  
 `INTMAX_MAX` и `INTMAX_MIN` определены в stdint.h.  
  
 Если `nptr` имеет значение `NULL` или `base` отлично от нуля или либо меньше 2 или больше 36, то параметр `errno` получает значение `EINVAL`.  
  
 Дополнительные сведения о кодах возврата см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `strtoimax` преобразует `nptr` в `intmax_t`.  версия двухбайтового символа `strtoimax` — `wcstoimax`; ее аргумент `nptr` — строка двухбайтовых символов.  В противном случае эти функции ведут себя идентично.  Обе функции прекращают чтение строки `nptr` на первом знаке, который они не могут распознать как часть числа.  Это может быть конечный символ null или первый числовой символ, больше или равный `base`.  
  
 Параметр категории `LC_NUMERIC` языкового стандарта определяет распознавание символа системы счисления в `nptr`; дополнительные сведения см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Функции, не имеющие суффикса `_l`, используют текущий языковой стандарт; `_strtoimax_l` и `_wcstoimax_l` идентичны соответствующим функциям, которые не имеют суффикса `_l`, за исключением того, что они используют переданный им языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если значение параметра `endptr` отлично от `NULL`, то указатель на символ, из\-за которого было прекращено сканирование, сохраняется в расположении, на которое указывает параметр `endptr`.  Если выполнить преобразование невозможно \(не были найдены допустимые цифры, или было указано недопустимое основание\), значение `nptr` сохраняется в расположении, на которое указывает параметр `endptr`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcstoimax`|`strtoimax`|`strtoimax`|`wcstoimax`|  
|`_tcstoimax_l`|`strtoimax_l`|`_strtoimax_l`|`_wcstoimax_l`|  
  
 `strtoimax` ожидает, что `nptr` указывает на строку следующей формы:  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits` &#124; `letters`\]  
  
 `whitespace` может состоять из пробелов и символов табуляции, которые игнорируются; `digits` — одна или несколько десятичных цифр; `letters` — одна или несколько букв от "a" до "z" \(или от "A" до "Z"\).  Первый символ, который не удовлетворяет этой форме, прекращает сканирование.  Если `base` от 2 до 36, то он используется как основание системы счисления.  Если значение `base` равно 0, то начальные символы строки, указанной в `nptr` используются для идентификации базы.  Если первый символ — «0», а второй символ не равен «x» или «x», строка интерпретируется как восьмеричное целое число.  Если первый символ — «0», а второй символ не равен «x» или «x», строка интерпретируется как шестнадцатеричное целое число.  Если первый символ от «1» до «9», строка интерпретируется как десятичное целое число.  Буквы от «а» до «z» присваиваются значения от 10 до 35; разрешены только буквы с присвоенными значениями меньше `base`.  Первый символ вне диапазона базы останавливает сканирование.  Например, если `base` — 0 и первый сканированный символ — «0», то восьмеричное целое число предполагается и символ «8» или «9» останавливает сканирование.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strtoimax`, `_strtoimax_l`, `wcstoimax`, `_wcstoimax_l`|\<inttypes.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoumax, \_strtoumax\_l, wcstoumax, \_wcstoumax\_l](../Topic/strtoumax,%20_strtoumax_l,%20wcstoumax,%20_wcstoumax_l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)