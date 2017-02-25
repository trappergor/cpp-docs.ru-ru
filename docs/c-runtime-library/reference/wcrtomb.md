---
title: "wcrtomb | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcrtomb"
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
  - "wcrtomb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "знаки, преобразование"
  - "многобайтовая кодировка"
  - "wcrtomb - функция"
  - "расширенные символы, преобразование"
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# wcrtomb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует расширенный символ в его представление в многобайтовом символе.  Существует более безопасная версия этой функции; см. раздел [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md).  
  
## Синтаксис  
  
```  
size_t wcrtomb(  
   char *mbchar,  
   wchar_t wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcrtomb(  
   char (&mbchar)[size],  
   wchar_t wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `mbchar`  
 Полученный преобразованный многобайтовый символ.  
  
 \[входящий\] `wchar`  
 Расширенный символ, который необходимо преобразовать.  
  
 \[входящий\] `mbstate`  
 Указатель на объект `mbstate_t`.  
  
## Возвращаемое значение  
 Возвращает число байтов, необходимое для представления преобразованного многобайтового символа; в противном случае — значение \-1 при возникновении ошибки.  
  
## Заметки  
 Функция `wcrtomb` преобразует расширенный символ, начиная с определенного состояния преобразования, которое содержится в `mbstate`, из значения, содержащегося в `wchar`, по адресу, представленному в `mbchar`.  Возвращает количество байтов, необходимое для представления соответствующего многобайтового символа, но не возвращает больше `MB_CUR_MAX` байтов.  
  
 Если `mbstate` принимает значение NULL, используется внутренний объект `mbstate_t`, содержащий состояние преобразования `mbchar`.  Если последовательность знаков `wchar` не имеет соответствующего многобайтового представления, то возвращается \-1 и `errno` принимает значение `EILSEQ`.  
  
 Функция `wcrtomb` отличается от [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) возможностью перезапуска.  Состояние преобразования хранится в `mbstate` для последующих вызовов тех же или других прерываемых функций.  Результаты не определены, когда происходит смешивание прерываемых и непрерываемых функций.  Например, приложение скорее будет использовать `wcsrlen` вместо `wcsnlen`, если последующий вызов `wcsrtombs` использовался вместо `wcstombs`.  
  
 В C\+\+ эта функция имеет шаблонную перегрузку, которая вызывает более новые и безопасные аналоги этой функции.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
## Исключения  
 Функция `wcrtomb` безопасна с точки зрения многопоточности, если ни одна из функций в данном потоке не вызывает `setlocale`, когда эта функция выполняется и пока `mbstate` имеет значение NULL.  
  
## Пример  
  
```  
// crt_wcrtomb.c  
// compile with: /W3  
// This program converts a wide character  
// to its corresponding multibyte character.  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    size_t      sizeOfCovertion = 0;  
    mbstate_t   mbstate;  
    char        mbStr = 0;  
    wchar_t*    wcStr = L"Q";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996  
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead  
    if (sizeOfCovertion > 0)  
    {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wcStr);  
        printf(" was converted to the \"%c\" ", mbStr);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
  **The corresponding wide character "Q" was converted to the "Q" multibyte character.**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`wcrtomb`|\<wchar.h\>|  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)