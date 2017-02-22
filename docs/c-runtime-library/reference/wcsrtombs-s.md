---
title: "wcsrtombs_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcsrtombs_s"
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
  - "wcsrtombs_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "преобразование строк, расширенные символы"
  - "wcsrtombs_s - функция"
  - "расширенные символы, строки"
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# wcsrtombs_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразовать строку расширенных символов в строку многобайтовых символов.  Это версия [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `pReturnValue`  
 Количество символов для преобразования.  
  
 \[исходящий\] `mbstr`  
 Адрес буфера для результирующей преобразованной строки многобайтовых символов.  
  
 \[исходящий\] `sizeInBytes`  
 Размер буфера `mbstr` \(в байтах\).  
  
 \[входящий\] `wcstr`  
 Указывает на преобразуемую строку расширенных символов.  
  
 \[входящий\] `count`  
 Максимальное количество байт, сохраняемых в буфере `mbstr` или [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 \[входящий\] `mbstate`  
 Указатель на объект состояния преобразования `mbstate_t`.  
  
## Возвращаемое значение  
 Нуль, если успешно; код ошибки при неудаче.  
  
|Условие ошибки.|Возвращает значение и `errno`|  
|---------------------|-----------------------------------|  
|`mbstr` содержит значение `NULL` и `sizeInBytes` \> 0|`EINVAL`|  
|Параметр `wcstr` содержит значение `NULL`|`EINVAL`|  
|Буфер назначения слишком мал, чтобы вместить преобразованную строку \(иначе `count` будет `_TRUNCATE`; см. примечания ниже\)|`ERANGE`|  
  
 Если срабатывает какое\-либо из этих условий, то возникает исключение о недопустимом параметре, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, то функция возвращает код ошибки и устанавливает `errno` как показано в таблице.  
  
## Заметки  
 Функция `wcsrtombs_s` преобразовывает строку расширенных символов, указанных в `wcstr`, в многобайтовые символы, сохраняющиеся в буфере, на который указывает `mbstr`, используя состояние преобразования, содержащееся в `mbstate`.  Преобразование будет продолжаться для каждого символа до тех пор, пока одно не будет выполнено одно из следующих условий:  
  
-   Не встретится расширенный символ null  
  
-   Встретится расширенный символ, который нельзя преобразовать  
  
-   Число байт, сохраненных в буфере `mbstr` не станет равным `count`.  
  
 Строка назначения всегда содержит завершающий null \(даже в случае ошибки\).  
  
 Если `count` является специальным значением [\_TRUNCATE](../../c-runtime-library/truncate.md), то преобразование `wcsrtombs_s` будет выполняться до тех пор, пока буфер назначения не будет заполнен с учетом завершающего признака null.  
  
 Если `wcsrtombs_s` успешно выполнит преобразование исходной строки, то значение, содержащее размер преобразованной строки в байтах с учетом завершающего символа конца строки null, будет помещено в `*``pReturnValue` \(предоставленное значение `pReturnValue` не равно `NULL`\).  Это происходит даже если аргумент `mbstr` равен `NULL`, таким образом, предоставляя возможность задать необходимый размер буфера.  Обратите внимание, что если `mbstr` равен `NULL`, то `count` игнорируется.  
  
 Если `wcsrtombs_s` обнаруживает расширенный символ, который не может преобразовать в многобайтовый, то в `*``pReturnValue` помещается значение \-1, буфер назначения устанавливается равным пустой строке, `errno` устанавливается в `EILSEQ`, и возвращается `EILSEQ`.  
  
 Если последовательности, на которые указывают `wcstr` и `mbstr`, перекрываются, то поведение `wcsrtombs_s` не определено.  `wcsrtombs_s` зависит от категории LC\_TYPE текущего языкового стандарта.  
  
> [!IMPORTANT]
>  Убедитесь, что `wcstr` и `mbstr` не перекрываются, и что `count` правильно отражает количество расширенных символов для преобразования.  
  
 Функция `wcsrtombs_s` отличается от [wcstombs\_s, \_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md) возможностью перезапуска.  Состояние преобразования хранится в `mbstate` для последующих вызовов тех же или других прерываемых функций.  Результаты не определены, когда происходит смешивание прерываемых и непрерываемых функций.  Например, приложение скорее будет использовать `wcsrlen` вместо `wcslen`, если последующий вызов `wcsrtombs_s` использовался вместо `wcstombs_s.`  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
## Исключения  
 Функция `wcsrtombs_s` безопасна с точки зрения многопоточности, если ни одна из функций в данном потоке не вызывает `setlocale`, когда эта функция выполняется и `mbstate` равно NULL.  
  
## Пример  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
  **Строка была успешно преобразована.**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`wcsrtombs_s`|\<wchar.h\>|  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)