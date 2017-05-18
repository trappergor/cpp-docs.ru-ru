---
title: "sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __swprintf_l
- sprintf
- _sprintf_l
- _swprintf_l
- swprintf
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
- ntdll.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _stprintf_l
- __swprintf_l
- sprintf_l
- swprintf
- _sprintf_l
- sprintf
- _stprintf
- stprintf_l
dev_langs:
- C++
helpviewer_keywords:
- _swprintf_l function
- _stprintf function
- __swprintf_l function
- stprintf function
- sprintf function
- _sprintf_l function
- _stprintf_l function
- swprintf function
- strings [C++], writing to
- _CRT_NON_CONFORMING_SWPRINTFS
- swprintf_l function
- stprintf_l function
- sprintf_l function
- formatted text [C++]
ms.assetid: f6efe66f-3563-4c74-9455-5411ed939b81
caps.latest.revision: 36
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 0a584008d0697dda3e45d8bafa74128d1978d5ce
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="sprintf-sprintfl-swprintf-swprintfl-swprintfl"></a>sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l
Запись форматированных данных в строку. Существуют более безопасные версии этих функций; см. раздел [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md). Безопасные версии `swprintf` и `_swprintf_l` не принимают параметр `count`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int sprintf(  
   char *buffer,  
   const char *format [,  
   argument] ...   
);  
int _sprintf_l(  
   char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int swprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format [,  
   argument]...  
);  
int _swprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
int __swprintf_l(  
   wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int sprintf(  
   char (&buffer)[size],  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _sprintf_l(  
   char (&buffer)[size],  
   const char *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Место хранения выходных данных  
  
 `count`  
 Максимальное количество символов, которое может хранить эта функция в версии Юникод.  
  
 `format`  
 Строка управления форматом  
  
 `argument`  
 Необязательные аргументы  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число записанных символов, или -1, если произошла ошибка. Если параметр `buffer` или `format` является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если разрешается продолжать выполнение, эти функции возвращают -1 и задают `errno` значение `EINVAL`.  
  
 `sprintf` возвращает число байтов, сохраненных в `buffer` без учета завершающего символа null. `swprintf` возвращает число расширенных символов, сохраненных в `buffer`, без учета завершающего расширенного символа null.  
  
## <a name="remarks"></a>Примечания  
 Функция `sprintf` форматирует и сохраняет набор символов и значений в `buffer`. Каждый `argument` (если он есть) преобразуется и выводится согласно соответствующей спецификацией формата в `format`. Формат состоит из обычных символов и имеет те же форму и функциональные возможности, что и аргумент `format` для [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). После последнего написанного символа добавляется символ null. Если копирование производится между перекрывающимися строками, поведение не определено.  
  
> [!IMPORTANT]
>  Функция `sprintf` не позволяет ограничить число записываемых символов, а значит, код, включающий функцию `sprintf`, может привести к переполнению буфера. Можно воспользоваться родственной функцией [_snprintf](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md), которая определяет максимальное количество символов для записи в `buffer`, или функцией [_scprintf](../../c-runtime-library/reference/scprintf-scprintf-l-scwprintf-scwprintf-l.md), позволяющей установить необходимый размер буфера. Кроме того, убедитесь, что `format` не является строкой, определяемой пользователем.  
  
 `swprintf` — это двухбайтовая версия `sprintf`; аргументы указателя для `swprintf` представляют собой двухбайтовые строки. Обнаружение ошибок кодирования в `swprintf` может отличаться от обнаружения ошибок в `sprintf`. `swprintf` и `fwprintf` ведут себя одинаково за тем исключением, что `swprintf` записывает выходные данные в строку, а не в назначение типа `FILE`, а `swprintf` требует настройки параметра `count`, определяющего максимальное количество символов для записи. Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
 `swprintf` соответствует стандарту ISO C, который требует указания второго параметра (`count`) типа `size_t`. Чтобы применить нестандартное поведение принудительно, определите функцию `_CRT_NON_CONFORMING_SWPRINTFS`. В будущей версии старое поведение может быть удалено, поэтому код необходимо изменить в соответствии с новым стандартным поведением.  
  
 В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stprintf`|`sprintf`|`sprintf`|`_swprintf`|  
|`_stprintf_l`|`_sprintf_l`|`_sprintf_l`|`__swprintf_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`sprintf`, `_sprintf_l`|\<stdio.h>|  
|`swprintf`, `_swprintf_l`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_sprintf.c  
// compile with: /W3  
// This program uses sprintf to format various  
// data and place them in the string named buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf( buffer,     "   String:    %s\n", s ); // C4996  
   j += sprintf( buffer + j, "   Character: %c\n", c ); // C4996  
   j += sprintf( buffer + j, "   Integer:   %d\n", i ); // C4996  
   j += sprintf( buffer + j, "   Real:      %f\n", fp );// C4996  
   // Note: sprintf is deprecated; consider using sprintf_s instead  
  
   printf( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
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
// crt_swprintf.c  
// wide character example  
// also demonstrates swprintf returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf fails because string contains WEOF (\xffff)  
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
