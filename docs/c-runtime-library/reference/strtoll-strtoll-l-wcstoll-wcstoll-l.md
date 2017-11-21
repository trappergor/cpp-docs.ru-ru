---
title: "Функции strtoll, _strtoll_l, wcstoll, _wcstoll_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strtoll
- wcstoll
- _strtoll_l
- _wcstoll_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strtoll_l
- _tcstoll_l
- _tcstoll
- _wcstoll_l
- strtoll
- wcstoll
dev_langs: C++
helpviewer_keywords:
- _tcstoll_l function
- _wcstoll_l function
- strtoll function
- wcstoll function
- _tcstoll function
- _strtoll_l function
ms.assetid: e2d05dcf-d3b2-4291-9e60-dee77e540fd7
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0c0528427216f08723d67cb56018a3379562cf32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="strtoll-strtolll-wcstoll-wcstolll"></a>strtoll, _strtoll_l, wcstoll, _wcstoll_l
Преобразуют строку в число `long long`.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `nptr`  
 Строка, завершающаяся символом NULL, для преобразования.  
  
 `endptr`  
 Указатель на символ, который останавливает сканирование.  
  
 `base`  
 Используемое числовое основание.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `strtoll` возвращает значение, представленное в строке `nptr`, кроме случаев, когда представление вызвало бы переполнение. В таких случаях возвращается значение `LLONG_MAX` или `LLONG_MIN`. Функция возвращает 0, если преобразование не может быть выполнено. Функция `wcstoll` возвращает значения аналогично функции `strtoll`.  
  
 Значения `LLONG_MAX` и `LLONG_MIN` определяются в LIMITS.H.  
  
 Если `nptr` имеет значение `NULL` или `base` имеет ненулевое значение и либо меньше 2, либо больше 36, то для `errno` устанавливается значение `EINVAL`.  
  
 Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `strtoll` преобразует `nptr` в `long long`. Обе функции прекращают чтение строки `nptr` на первом знаке, который они не могут распознать как часть числа. Это может быть завершающий нуль-символ или первый числовой символ, который больше или равен `base`. Функция `wcstoll` — это версия функции `strtoll` с расширенными символами. Ее аргумент `nptr` — строка расширенных символов. В остальном эти функции работают одинаково.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoll`|`strtoll`|`strtoll`|`wcstoll`|  
|`_tcstoll_l`|`_strtoll_l`|`_strtoll_l`|`_wcstoll_l`|  
  
 Параметр категории `LC_NUMERIC` языкового стандарта определяет распознавание символа основания системы счисления в `nptr`. Дополнительные сведения см. в разделе [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Функции, не имеющие суффикса `_l`, используют текущий языковой стандарт. Функции `_strtoll_l` и `_wcstoll_l` идентичны соответствующим функциям, которые не имеют суффикса, за исключением того, что они вместо этого используют переданный им языковой стандарт. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если `endptr` не является значением `NULL`, указатель на символ, который останавливает сканирование, хранится в расположении, на которое указывает `endptr`. Если не удается выполнить преобразование (не найдены допустимые цифры или указано недопустимое основание), значение `nptr` сохраняется в расположении, указанном `endptr`.  
  
 Функция `strtoll` ожидает, что `nptr` указывает на строку следующего вида:  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits` &#124; `letters`]  
  
 Строка `whitespace` может состоять из пробелов и символов табуляции, которые игнорируются. `digits` — одна или несколько десятичных цифр; `letters` — одна или несколько букв от a до z (или от A до Z). Первый символ, который не соответствует этой форме, останавливает сканирование. Если значение `base` лежит в диапазоне от 2 до 36, оно используется как основание системы счисления. Если `base` равно 0, то начальные символы строки, на которую указывает `nptr`, используются для определения основания. Если первый символ — 0, а второй символ не равен x или X, строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от а до z (или от А до Z) присваиваются значения от 10 до 35. Допускаются только буквы с присвоенными значениями меньше `base`. Первый символ за пределами диапазона основания останавливает сканирование. Например, если значение `base` равно 0 и первый считанный символ — 0, то предполагается восьмеричное целое число и символ 8 или 9 останавливает сканирование.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strtoll`, `_strtoll_l`|\<stdlib.h>|  
|`wcstoll`, `_wcstoll_l`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)