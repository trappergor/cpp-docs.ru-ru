---
title: "sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _swprintf_s_l
- _sprintf_s_l
- swprintf_s
- sprintf_s
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
apitype: DLLExport
f1_keywords:
- swprintf_s
- sprintf_s
- stdio/sprintf_s
- stdio/swprintf_s
- stdio/_sprintf_s_l
- stdio/_swprintf_s_l
- _sprintf_s_l
- _swprintf_s_l
dev_langs:
- C++
helpviewer_keywords:
- stprintf_s function
- stprintf_s_l function
- swprintf_s_l function
- sprintf_s function
- swprintf_s function
- _swprintf_s_l function
- sprintf_s_l function
- _stprintf_s_l function
- _stprintf_s function
- _sprintf_s_l function
- formatted text [C++]
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 06afe4f945413ae1f45ff9249dcec0cb87cab987
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="sprintfs-sprintfsl-swprintfs-swprintfsl"></a>sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l
Запись форматированных данных в строку. Это версии функций [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int sprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   ...   
);  
int _sprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale,  
   ...   
);  
int swprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   ...  
);  
int _swprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale,  
   ...  
);  
template <size_t size>  
int sprintf_s(  
   char (&buffer)[size],  
   const char *format,  
   ...   
); // C++ only  
template <size_t size>  
int swprintf_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   ...  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Место хранения выходных данных  
  
 `sizeOfBuffer`  
 Наибольшее число символов для хранения.  
  
 `format`  
 Строка управления форматом  
  
 `...`  
 Необязательные аргументы для форматирования  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число записанных символов, или -1, если произошла ошибка. Если `buffer` или `format` является пустым указателем, `sprintf_s` и `swprintf_s` возвращают значение -1 и задают `errno` равным `EINVAL`.  
  
 `sprintf_s` возвращает число байтов, сохраненных в `buffer`без учета завершающего символа null. `swprintf_s` возвращает число расширенных символов, сохраненных в `buffer`, без учета завершающего расширенного символа null.  
  
## <a name="remarks"></a>Примечания  
 Функция `sprintf_s` форматирует и сохраняет набор символов и значений в `buffer`. Каждый `argument` (если он есть) преобразуется и выводится согласно соответствующей спецификацией формата в `format`. Формат состоит из обычных символов и имеет те же форму и функциональные возможности, что и аргумент `format` для [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). После последнего написанного символа добавляется символ null. Если копирование производится между перекрывающимися строками, поведение не определено.  
  
 Основное различие между `sprintf_s` и `sprintf` заключается в том, что `sprintf_s` проверяет строку форматирования на наличие допустимых символов форматирования, тогда как `sprintf` только проверяет, является ли строка формата или буфер указателем `NULL` . Если проверка завершается с ошибкой, то вызывается обработчик недопустимого параметра, как описано в разделе [Parameter Validation](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает -1 и устанавливает `errno` в значение `EINVAL`.  
  
 Другое основное различие между `sprintf_s` и `sprintf` в том, что `sprintf_s` принимает параметр длины, определяющий размер буфера вывода в символах. Если буфер слишком мал для форматированного текста, включая завершающий символ null, то ему присваивается пустая строка путем размещения символа null в `buffer``[0]`и вызывается обработчик недопустимого параметра. В отличие от `_snprintf`, `sprintf_s` гарантирует, что буфер будет завершен символом null (если размер буфера не равен нулю).  
  
 `swprintf_s` — это двухбайтовая версия `sprintf_s`; аргументы указателя для `swprintf_s` представляют собой двухбайтовые строки. Обнаружение ошибок кодирования в `swprintf_s` может отличаться от обнаружения ошибок в `sprintf_s`. Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
 В C++ использование этих функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера, что исключает необходимость указания аргумента с размером буфера, а также они могут автоматически заменять более старые незащищенные функции их новыми безопасными аналогами. Для получения дополнительной информации см. [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
 Существуют версии `sprintf_s` , которые обеспечивают дополнительный контроль над происходящим, если буфер слишком мал. Дополнительные сведения см. в разделе [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stprintf_s`|`sprintf_s`|`sprintf_s`|`swprintf_s`|  
|`_stprintf_s_l`|`_sprintf_s_l`|`_sprintf_s_l`|`_swprintf_s_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`sprintf_s`, `_sprintf_s_l`|C: \<stdio.h><br /><br /> C++: \<cstdio> или \<stdio.h>|  
|`swprintf_s`, `_swprintf_s_l`|C: \<stdio.h> или \<wchar.h><br /><br /> C++: \<cstdio>, \<cwchar>, \<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_sprintf_s.c  
// This program uses sprintf_s to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf_s( buffer, 200,     "   String:    %s\n", s );  
   j += sprintf_s( buffer + j, 200 - j, "   Character: %c\n", c );  
   j += sprintf_s( buffer + j, 200 - j, "   Integer:   %d\n", i );  
   j += sprintf_s( buffer + j, 200 - j, "   Real:      %f\n", fp );  
  
   printf_s( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
}  
```  
  
```Output  
Output:  
   String:    computer  
   Character: l  
   Integer:   35  
   Real:      1.732053  
  
character count = 79  
```  
  
## <a name="example"></a>Пример  
  
```  
// crt_swprintf_s.c  
// wide character example  
// also demonstrates swprintf_s returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf_s( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf_s( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf_s fails because string contains WEOF (\xffff)  
   printf( "wrote %d characters\n", len );  
}  
```  
  
```Output  
wrote 11 characters  
wrote -1 characters  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)
