---
title: "wcsrtombs | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcsrtombs"
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
  - "wcsrtombs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Функция wcsrtombs"
  - "преобразование строк, расширенные символы"
  - "расширенные символы, строки"
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcsrtombs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразовать строку расширенных символов в строку многобайтовых символов.  Существует более безопасная версия этой функции; см. раздел [wcsrtombs\_s](../../c-runtime-library/reference/wcsrtombs-s.md).  
  
## Синтаксис  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `mbstr`  
 Расположение адреса результирующей преобразованной многобайтовой символьной строки.  
  
 \[входящий\] `wcstr`  
 Косвенно указывает на расположение расширенной символьной строки, которую требуется преобразовать.  
  
 \[входящий\] `count`  
 Число символов для преобразования.  
  
 \[входящий\] `mbstate`  
 Указатель на объект состояния преобразования `mbstate_t`.  
  
## Возвращаемое значение  
 Возвращает число успешно преобразованных байтов, не учитывая завершающий нулевой символ \(если есть\), или \-1, если возникла ошибка.  
  
## Заметки  
 Функция `wcsrtombs` преобразует строку расширенных символов, начиная в определенном состоянии преобразования, содержащемся в `mbstate`, из значений, косвенно указанных `wcstr`, в адрес `mbstr`.  Преобразование будет продолжаться для каждого символа до тех пор, пока: не встречен расширенный завершающий нулевой символ, не встречен несоответствующий символ или не превышено ограничение `count`.  Если `wcsrtombs` встречает расширенный нуль\-символ \(L'\\0\) либо перед, либо после `count` символов, она преобразовывает его в 8\-и битный 0 и останавливается.  
  
 Таким образом, символьная многобайтовая строка `mbstr` завершается нуль\-символом, только если `wcsrtombs` встречает расширенный нулевой символ во время преобразования.  Если последовательности, на которые указывают `wcstr` и `mbstr`, перекрываются, то поведение `wcsrtombs` не определено.  `wcsrtombs` зависит от категории LC\_TYPE текущего языкового стандарта.  
  
 Функция `wcsrtombs` отличается от [wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md) возможностью перезапуска.  Состояние преобразования хранится в `mbstate` для последующих вызовов тех же или других прерываемых функций.  Результаты не определены, когда происходит смешивание прерываемых и непрерываемых функций.  Например, приложение скорее будет использовать `wcsrlen` вместо `wcsnlen`, если последующий вызов `wcsrtombs` использовался вместо `wcstombs`.  
  
 Если аргумент `mbstr` равен `NULL`, `wcsrtombs` возвращает необходимый размер в байтах строки назначения.  Если `mbstate` имеет значение NULL, используется внутреннее состояние преобразования `mbstate_t`.  Если последовательность знаков `wchar` не имеет соответствующего многобайтового представления, то возвращается \-1 и `errno` принимает значение `EILSEQ`.  
  
 В C\+\+ эта функция имеет шаблонную перегрузку, которая вызывает более новые и безопасные аналоги этой функции.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
## Исключения  
 Функция `wcsrtombs` безопасна с точки зрения многопоточности, если ни одна из функций в данном потоке не вызывает `setlocale`, когда эта функция выполняется и `mbstate` имеет значение не NULL.  
  
## Пример  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
  **The string was successfuly converted.**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`wcsrtombs`|\<wchar.h\>|  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)