---
title: "Функции _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _strtoui64
- _strtoui64_l
- _wcstoui64
- _wcstoui64_l
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
- _wcstoui64_l
- strtoui64_l
- wcstoui64
- _wcstoui64
- _strtoui64_l
- strtoui64
- _strtoui64
- wcstoui64_l
dev_langs:
- C++
helpviewer_keywords:
- _strtoui64_l function
- _wcstoui64_l function
- string conversion, to integers
- wcstoui64_l function
- _strtoui64 function
- _wcstoui64 function
- wcstoui64 function
- strtoui64_l function
- strtoui64 function
ms.assetid: 7fcb537e-4554-4ceb-a5b6-bc09244e72ef
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ad6ce06ef428005ea07214b426df0c61f623429
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="strtoui64-wcstoui64-strtoui64l-wcstoui64l"></a>_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l
Преобразуют строку в значение `__int64`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 _strtoui64(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned __int64 _wcstoui64(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned __int64 _strtoui64_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned __int64 _wcstoui64(  
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
 Функция `_strtoui64` возвращает значение, представленное в строке `nptr`, кроме случаев, когда представление вызвало бы переполнение. В этом случае возвращается значение `_UI64_MAX`. Функция `_strtoui64` возвращает 0, если преобразование не может быть выполнено.  
  
 Значение `_UI64_MAX` определяется в LIMITS.H.  
  
 Если `nptr` имеет значение `NULL` или `base` имеет ненулевое значение и либо меньше 2, либо больше 36, то для `errno` устанавливается значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [Функции _doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 `_strtoui64` Функция преобразует `nptr` для `unsigned` `__int64`. Функция `_wcstoui64` — это версия функции `_strtoui64` с расширенными символами. Ее аргумент `nptr` — строка расширенных символов. В остальном эти функции работают одинаково.  
  
 Обе функции прекращают чтение строки `nptr` на первом знаке, который они не могут распознать как часть числа. Это может быть конечный нуль-символ или первый числовой символ, который больше или равен `base`.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoui64`|`_strtoui64`|`_strtoui64`|`_wstrtoui64`|  
|`_tcstoui64_l`|`_strtoui64_l`|`_strtoui64_l`|`_wstrtoui64_l`|  
  
 Параметр категории `LC_NUMERIC` текущего языкового стандарта определяет распознавание символа основания системы счисления в `nptr`. Дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Функции без суффикса _l используют текущий языковой стандарт; `_strtoui64_l` и `_wcstoui64_l` идентичны соответствующим функциям без `_l` суффикса, за исключением того, что они используют переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
 Если `endptr` не является значением `NULL`, указатель на символ, который останавливает сканирование, хранится в расположении, на которое указывает `endptr`. Если не удается выполнить преобразование (не найдены допустимые цифры или указано недопустимое основание), значение `nptr` сохраняется в расположении, указанном `endptr`.  
  
 Функция `_strtoui64` ожидает, что `nptr` указывает на строку следующего вида:  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{`x` &#124; `X`}]] [`digits`]  
  
 `whitespace` может состоять из пробелов и символов табуляции, которые игнорируются. `digits` — одна или несколько десятичных цифр. Первый символ, который не соответствует этой форме, останавливает сканирование. Если значение `base` лежит в диапазоне от 2 до 36, оно используется как основание системы счисления. Если `base` равно 0, то начальные символы строки, на которую указывает `nptr`, используются для определения основания. Если первый символ — "0", а второй символ не равен "x" или "X", строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от а до z (или от А до Z) присваиваются значения от 10 до 35. Допускаются только буквы с присвоенными значениями меньше `base`. Первый символ за пределами диапазона основания останавливает сканирование. Например, если значение `base` равно 0 и первый считанный символ — "0", то предполагается восьмеричное целое число и символ "8" или "9" останавливает чтение.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_strtoui64`|\<stdlib.h>|  
|`_wcstoui64`|\<stdlib.h> или \<wchar.h>|  
|`_strtoui64_l`|\<stdlib.h>|  
|`_wcstoui64_l`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_strtoui64.c  
#include <stdio.h>  
  
unsigned __int64 atoui64(const char *szUnsignedInt) {  
   return _strtoui64(szUnsignedInt, NULL, 10);  
}  
  
int main() {  
   unsigned __int64 u = atoui64("18446744073709551615");  
   printf( "u = %I64u\n", u );  
}  
```  
  
```Output  
u = 18446744073709551615  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)