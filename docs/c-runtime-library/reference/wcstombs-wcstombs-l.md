---
title: "wcstombs, _wcstombs_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcstombs
- _wcstombs_l
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
- wcstombs
- _wcstombs_l
dev_langs:
- C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: dead533ee11db7c40faa7d3611b30c6a6159ee50
ms.lasthandoff: 02/24/2017

---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l
Преобразует последовательность расширенных символов в соответствующую последовательность многобайтовых символов. Существуют более безопасные версии этих функций; см. раздел [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t wcstombs(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count   
);  
size_t _wcstombs_l(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t wcstombs(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _wcstombs_l(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 `mbstr`  
 Адрес последовательности многобайтовых символов.  
  
 `wcstr`  
 Адрес последовательности расширенных символов.  
  
 `count`  
 Максимальное количество байтов, которые могут храниться в выходной строке многобайтовых символов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если функция `wcstombs` успешно преобразовывает строку многобайтовых символов, она возвращает число байтов, записанных в выходную строку многобайтовых символов, исключая конечный символ `NULL` (при его наличии). Если аргумент `mbstr` равен `NULL`, функция `wcstombs` возвращает необходимый размер строки назначения в байтах. Если функция `wcstombs` встречает расширенный символ, который она не может преобразовать в многобайтовый символ, возвращается значение –1, приведенное к типу `size_t`, и для параметра `errno` задается значение `EILSEQ`.  
  
## <a name="remarks"></a>Примечания  
 Функция `wcstombs` преобразовывает строку расширенных символов, на которую указывает параметр `wcstr`, в соответствующие многобайтовые символы и сохраняет результаты в массиве `mbstr`. Параметр `count` указывает максимальное число байтов, которые могут храниться в выходной строке многобайтовых символов (т. е., размер `mbstr`). Как правило, количество байтов, необходимое для преобразования строки расширенных символов, неизвестно. Для некоторых расширенных символов требуется только один байт в выходной строке; для других требуется два байта. Если в выходной строке многобайтовых символов предусмотреть по два байта на каждый расширенный символ из входной строки (включая расширенный символ `NULL`), то результат гарантированно поместится.  
  
 Если функция `wcstombs` встречает расширенный нуль-символ (L"\0") перед или после `count` символов, она преобразовывает его в 8-битный 0 и останавливается. Таким образом, строка многобайтовых символов `mbstr` завершается нуль-символом только в том случае, если функция `wcstombs` встречает расширенный нуль-символ во время преобразования. Если последовательности, на которые указывают параметры `wcstr` и `mbstr`, перекрываются, то поведение `wcstombs` не определено.  
  
 Если аргумент `mbstr` равен `NULL`, функция `wcstombs` возвращает необходимый размер строки назначения в байтах.  
  
 Функция `wcstombs` проверяет свои параметры. Если параметр `wcstr` имеет значение `NULL` или значение `count` больше `INT_MAX`, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция устанавливает параметр `errno` в значение `EINVAL` и возвращает –1.  
  
 Функция `wcstombs` использует текущий языковой стандарт для любых аспектов поведения, зависящих от языкового стандарта; функция `_wcstombs_l` идентична за исключением того, что она использует переданный языковой стандарт. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`wcstombs`|\<stdlib.h>|  
|`_wcstombs_l`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 Эта программа иллюстрирует поведение функции `wcstombs`.  
  
```  
// crt_wcstombs.c  
// compile with: /W3  
// This example demonstrates the use  
// of wcstombs, which converts a string  
// of wide characters to a string of   
// multibyte characters.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t  count;  
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t *pWCBuffer = L"Hello, world.";  
  
    printf("Convert wide-character string:\n" );  
  
    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s instead  
    printf("   Characters converted: %u\n",  
            count );  
    printf("    Multibyte character: %s\n\n",  
           pMBBuffer );  
  
    free(pMBBuffer);  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 13  
    Multibyte character: Hello, world.  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
