---
title: "wcrtomb_s | Microsoft Docs"
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
  - "wcrtomb_s"
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
  - "wcrtomb_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "расширенные символы, преобразование"
  - "wcrtomb_s - функция"
  - "многобайтовая кодировка"
  - "символы, преобразование"
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcrtomb_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразуйте расширенный символ в представление в многобайтовой кодировке. Версия [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char *mbchar,  
   size_t sizeOfmbchar,  
   wchar_t *wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char (&mbchar)[size],  
   wchar_t *wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Параметры  
 \[выходной\] `pReturnValue`  
 Возвращает число записанных байтов или \-1, если произошла ошибка.  
  
 \[выходной\] `mbchar`  
 Полученный многобайтовых преобразовать символ.  
  
 \[in\] `sizeOfmbchar`  
 Размер `mbchar` переменной в байтах.  
  
 \[in\] `wchar`  
 Расширенный символ для преобразования.  
  
 \[in\] `mbstate`  
 Указатель на объект `mbstate_t`.  
  
## Возвращаемое значение  
 Возвращает нуль или `errno` значение, если происходит ошибка.  
  
## Заметки  
 `wcrtomb_s` Функция преобразует строку расширенных символов, начиная с указанного преобразования состоянием, содержащимся в `mbstate`, из значения, содержащегося в `wchar`, в адрес, представленного `mbchar`.`pReturnValue` Значение будет число байт преобразуется, но не более чем `MB_CUR_MAX` байт или \-1, если произошла ошибка.  
  
 Если `mbstate` имеет значение null, внутренний `mbstate_t` используется состояние преобразования. Если символ содержится в `wchar` отсутствует соответствующий Многобайтовый символ значение `pReturnValue` равно\-1, и функция возвращает `errno` значение `EILSEQ`.  
  
 `wcrtomb_s` Функция отличается от [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) с возможностью перезапуска. Состояние преобразования хранится в переменной `mbstate` для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, приложение будет использовать `wcsrlen` вместо `wcslen`, если в последующем вызове `wcsrtombs_s` были использованы вместо `wcstombs_s.`  
  
 В C\+\+ с помощью этой функции упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером\) и они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Для получения дополнительной информации см. [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
## Исключения  
 `wcrtomb_s` Функция является потокобезопасной, при условии, что функции в текущем потоке не вызывает `setlocale` во время выполнения этой функции и `mbstate` имеет значение null.  
  
## Пример  
  
```  
// crt_wcrtomb_s.c  
// This program converts a wide character  
// to its corresponding multibyte character.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    errno_t     returnValue;  
    size_t      pReturnValue;  
    mbstate_t   mbstate;  
    size_t      sizeOfmbStr = 1;  
    char        mbchar = 0;  
    wchar_t*    wchar = L"Q\0";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),  
                            *wchar, &mbstate);  
    if (returnValue == 0) {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wchar);  
        printf(" was converted to a the \"%c\" ", mbchar);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
```Output  
Соответствующий расширенный символ «Q» был преобразован в многобайтовые кодировки «Q».  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`wcrtomb_s`|\<wchar.h\>|  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)