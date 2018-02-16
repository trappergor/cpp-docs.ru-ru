---
title: "strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- wcstoimax
- _wcstoimax_l
- _strtoimax_l
- strtoimax
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
- wcstoimax
- _tcstoimax
- strtoimax
- _wcstoimax_l
- _strtoimax_l
- _tcstoimax_l
dev_langs:
- C++
helpviewer_keywords:
- strtoimax funciton
- conversion functions
- _strtoimax_l function
- _wcstoimax_l function
- wcstoimax function
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4125ebf922ed3525d5efd6a92b1273ca18d0fd7d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="strtoimax-strtoimaxl-wcstoimax-wcstoimaxl"></a>strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l
Преобразует строку в целочисленное значение наибольшего поддерживаемого целочисленного типа со знаком.  
  
## <a name="syntax"></a>Синтаксис  
  
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
 `strtoimax` возвращает значение, представленное в строке `nptr`, кроме случаев, когда представление вызвало бы переполнение; в этом случае возвращается значение `INTMAX_MAX` или `INTMAX_MIN`, и `errno` устанавливается в значение `ERANGE`. Функция возвращает 0, если преобразование не может быть выполнено. `wcstoimax` возвращает значения аналогично `strtoimax`.  
  
 `INTMAX_MAX` и `INTMAX_MIN` задаются в STDLIB.H.  
  
 Если `nptr` имеет значение `NULL` или `base` имеет ненулевое значение и либо меньше 2, либо больше 36, то для `errno` устанавливается значение `EINVAL`.  
  
 Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `strtoimax` преобразует `nptr` в `intmax_t`. `wcstoimax` — это версия `strtoimax` с расширенными символами; ее аргумент `nptr` — строка расширенных символов. В остальном эти функции работают одинаково. Обе функции прекращают чтение строки `nptr` на первом знаке, который они не могут распознать как часть числа. Это может быть завершающий нуль-символ или первый числовой символ, который больше или равен `base`.  
  
 Параметр категории `LC_NUMERIC` языкового стандарта определяет распознавание символа основания системы счисления в `nptr`; дополнительные сведения см. в разделе [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Функции, не имеющие суффикс `_l`, используют текущий языковой стандарт; `_strtoimax_l` и `_wcstoimax_l` идентичны соответствующим функциям, которые не имеют суффикс `_l`, за исключением того, что они вместо этого используют переданный им языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
 Если `endptr` не является значением `NULL`, указатель на символ, который останавливает сканирование, хранится в расположении, на которое указывает `endptr`. Если не удается выполнить преобразование (не найдены допустимые цифры или указано недопустимое основание), значение `nptr` сохраняется в расположении, указанном `endptr`.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoimax`|`strtoimax`|`strtoimax`|`wcstoimax`|  
|`_tcstoimax_l`|`strtoimax_l`|`_strtoimax_l`|`_wcstoimax_l`|  
  
 Функция `strtoimax` ожидает, что `nptr` указывает на строку следующего вида:  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits` &#124; `letters`]  
  
 Строка `whitespace` может состоять из пробелов и символов табуляции, которые игнорируются. `digits` — одна или несколько десятичных цифр; `letters` — одна или несколько букв от a до z (или от A до Z). Первый символ, который не соответствует этой форме, останавливает сканирование. Если значение `base` лежит в диапазоне от 2 до 36, оно используется как основание системы счисления. Если `base` равно 0, то начальные символы строки, на которую указывает `nptr`, используются для определения основания. Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от а до z (или от А до Z) присваиваются значения от 10 до 35. Допускаются только буквы с присвоенными значениями меньше `base`. Первый символ за пределами диапазона основания останавливает сканирование. Например, если значение `base` равно 0 и первый считанный символ — "0", то предполагается восьмеричное целое число, и символ "8" или "9" остановит сканирование.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strtoimax`, `_strtoimax_l`, `wcstoimax`, `_wcstoimax_l`|\<inttypes.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l](../../c-runtime-library/reference/strtoumax-strtoumax-l-wcstoumax-wcstoumax-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)