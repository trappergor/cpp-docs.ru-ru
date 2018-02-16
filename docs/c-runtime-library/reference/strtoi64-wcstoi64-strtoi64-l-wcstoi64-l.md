---
title: "_strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _strtoi64
- _strtoi64_l
- _wcstoi64_l
- _wcstoi64
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
- _strtoi64
- strtoi64
- _stroi64_l
- _wcstoi64_l
- wcstoi64_l
- _wcstoi64
- wcstoi64
- strtoi64_l
dev_langs:
- C++
helpviewer_keywords:
- _strtoi64 function
- _wcstoi64 function
- _strtoi64_l function
- string conversion, to integers
- _wcstoi64_l function
- strtoi64_l function
- wcstoi64 function
- strtoi64 function
- wcstoi64_l function
ms.assetid: ea2abc50-7bfe-420e-a46b-703c3153593a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a383d53c762f4bd15d7a45288bb2ef4e7e452ee
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="strtoi64-wcstoi64-strtoi64l-wcstoi64l"></a>_strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l
Преобразуют строку в значение `__int64`.  
  
## <a name="syntax"></a>Синтаксис  
  
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
 `_strtoi64` возвращает значение, представленное в строке `nptr`, кроме случаев, когда представление вызвало бы переполнение; в этом случае возвращается значение `_I64_MAX` или `_I64_MIN`. Функция возвращает 0, если преобразование не может быть выполнено. Функция `_wcstoi64` возвращает значения аналогично функции `strtoi64`.  
  
 Значения `_I64_MAX` и `_I64_MIN` определяются в LIMITS.H.  
  
 Если `nptr` — `NULL` или `base` имеет ненулевое значение и либо меньше 2, либо больше 36, то `errno` устанавливается в значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [Функции _doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_strtoi64` преобразует `nptr` в `__int64`. Обе функции прекращают чтение строки `nptr` на первом знаке, который они не могут распознать как часть числа. Это может быть конечный нуль-символ или первый числовой символ, который больше или равен `base`. Функция `_wcstoi64` — это версия функции `_strtoi64` с расширенными символами. Ее аргумент `nptr` — строка расширенных символов. В остальном эти функции ведут себя одинаково.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoi64`|`_strtoi64`|`_strtoi64`|`_wcstoi64`|  
|`_tcstoi64_l`|`_strtoi64_l`|`_strtoi64_l`|`_wcstoi64_l`|  
  
 Параметр категории `LC_NUMERIC` языкового стандарта определяет распознавание символа основания системы счисления в `nptr`*;* дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Функции без суффикса _l используют текущий языковой стандарт; `_strtoi64_l` и `_wcstoi64_l` идентичны для соответствующей функции без `_l` суффикса, за исключением того, что они используют переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
 Если `endptr` не является значением `NULL`, указатель на символ, который останавливает сканирование, хранится в расположении, на которое указывает `endptr`. Если не удается выполнить преобразование (не найдены допустимые цифры или указано недопустимое основание), значение `nptr` сохраняется в расположении, указанном `endptr`.  
  
 Функция `_strtoi64` ожидает, что `nptr` указывает на строку следующего вида:  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{`x` &#124; `X`}]] [`digits`]  
  
 `whitespace` может состоять из пробелов и символов табуляции, которые игнорируются. `digits` — одна или несколько десятичных цифр. Первый символ, который не соответствует этой форме, останавливает сканирование. Если значение `base` лежит в диапазоне от 2 до 36, оно используется как основание системы счисления. Если `base` равно 0, то начальные символы строки, на которую указывает `nptr`, используются для определения основания. Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от а до z (или от А до Z) присваиваются значения от 10 до 35. Допускаются только буквы с присвоенными значениями меньше `base`. Первый символ за пределами диапазона основания останавливает сканирование. Например, если значение `base` равно 0 и первый считанный символ — "0", то предполагается восьмеричное целое число и символ "8" или "9" останавливает чтение.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_strtoi64`, `_strtoi64_l`|\<stdlib.h>|  
|`_wcstoi64`, `_wcstoi64_l`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)