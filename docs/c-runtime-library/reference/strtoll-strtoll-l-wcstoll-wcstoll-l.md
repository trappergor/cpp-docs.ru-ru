---
title: "strtoll, _strtoll_l, wcstoll, _wcstoll_l | Microsoft Docs"
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
  - "strtoll"
  - "wcstoll"
  - "_strtoll_l"
  - "_wcstoll_l"
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
  - "_strtoll_l"
  - "_tcstoll_l"
  - "_tcstoll"
  - "_wcstoll_l"
  - "strtoll"
  - "wcstoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoll_l - функция"
  - "_tcstoll - функция"
  - "_tcstoll_l - функция"
  - "_wcstoll_l - функция"
  - "strtoll - функция"
  - "wcstoll - функция"
ms.assetid: e2d05dcf-d3b2-4291-9e60-dee77e540fd7
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtoll, _strtoll_l, wcstoll, _wcstoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует строку в значение типа `long long`.  
  
## Синтаксис  
  
```  
long long strtoll(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
long long wcstoll(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
long long _strtoll_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
long long _wcstoll_l(  
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
 `strtoll` возвращает значение, которое представлено в строке `nptr`, кроме случаев, когда представление вызвало бы переполнение — в этом случае возвращается значение `LLONG_MAX` или `LLONG_MIN`.  Функция возвращает 0, если преобразование не может быть выполнено.  `wcstoll` возвращает значения аналогично `strtoll`.  
  
 `LLONG_MAX` и `LLONG_MIN` определены в LIMITS.H.  
  
 Если `nptr` имеет значение `NULL` или `base` отлично от нуля или либо меньше 2 или больше 36, то параметр `errno` получает значение `EINVAL`.  
  
 Дополнительные сведения о кодах возврата см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `strtoll` преобразовывает `nptr` в `long long`.  Обе функции прекращают чтение строки `nptr` на первом знаке, который они не могут распознать как часть числа.  Это может быть конечный символ null или первый числовой символ, больше или равный `base`.  `wcstoll` — это двухбайтовая версия `strtoll`; её аргумент `nptr` — строка двухбайтовых символов.  В противном случае эти функции ведут себя идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcstoll`|`strtoll`|`strtoll`|`wcstoll`|  
|`_tcstoll_l`|`_strtoll_l`|`_strtoll_l`|`_wcstoll_l`|  
  
 Параметр категории `LC_NUMERIC` языкового стандарта определяет распознавание символа системы счисления в `nptr`; дополнительные сведения см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Функции, не имеющие суффикса `_l`, используют текущий языковой стандарт; `_strtoll_l` и `_wcstoll_l` идентичны соответствующим функциям, которые не имеют суффикса, за исключением того, что они используют переданный им языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если значение параметра `endptr` отлично от `NULL`, то указатель на символ, из\-за которого было прекращено сканирование, сохраняется в расположении, на которое указывает параметр `endptr`.  Если выполнить преобразование невозможно \(не были найдены допустимые цифры, или было указано недопустимое основание\), значение `nptr` сохраняется в расположении, на которое указывает параметр `endptr`.  
  
 `strtoll` ожидает, что `nptr` указывает на строку следующей формы:  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits` &#124; `letters`\]  
  
 `whitespace` может состоять из пробелов и символов табуляции, которые игнорируются; `digits` — одна или несколько десятичных цифр; `letters` — одна или несколько букв от "a" до "z" \(или от "A" до "Z"\).  Первый символ, который не удовлетворяет этой форме, прекращает сканирование.  Если `base` от 2 до 36, то он используется как основание системы счисления.  Если значение `base` равно 0, то начальные символы строки, указанной в `nptr` используются для идентификации базы.  Если первый символ — «0», а второй символ не равен «x» или «x», строка интерпретируется как восьмеричное целое число.  Если первый символ — «0», а второй символ не равен «x» или «x», строка интерпретируется как шестнадцатеричное целое число.  Если первый символ от «1» до «9», строка интерпретируется как десятичное целое число.  Буквы от «а» до «z» присваиваются значения от 10 до 35; разрешены только буквы с присвоенными значениями меньше `base`.  Первый символ вне диапазона базы останавливает сканирование.  Например, если `base` — 0 и первый сканированный символ — «0», то восьмеричное целое число предполагается и символ «8» или «9» останавливает сканирование.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strtoll`, `_strtoll_l`|\<stdlib.h\>|  
|`wcstoll`, `_wcstoll_l`|\<stdlib.h\> или \<wchar.h\>|  
  
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
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)