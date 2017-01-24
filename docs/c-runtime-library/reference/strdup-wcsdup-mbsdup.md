---
title: "_strdup, _wcsdup, _mbsdup | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strdup"
  - "_mbsdup"
  - "_wcsdup"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcsdup"
  - "mbsdup"
  - "_mbsdup"
  - "_strdup"
  - "_ftcsdup"
  - "_wcsdup"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wcsdup - функция"
  - "ftcsdup - функция"
  - "_ftcsdup - функция"
  - "mbsdup - функция"
  - "strdup - функция"
  - "_strdup - функция"
  - "_wcsdup - функция"
  - "копирование строк"
  - "дублирование строк"
  - "Копирование строк [C++]"
  - "_mbsdup - функция"
  - "дублирование строк [C++]"
  - "tcsdup - функция"
  - "_tcsdup - функция"
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strdup, _wcsdup, _mbsdup
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Повторяющиеся строки.  
  
> [!IMPORTANT]
>  `_mbsdup` нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
char *_strdup(  
   const char *strSource   
);  
wchar_t *_wcsdup(  
   const wchar_t *strSource   
);  
unsigned char *_mbsdup(  
   const unsigned char *strSource   
);  
```  
  
#### Параметры  
 `strSource`  
 Исходная строка, завершающаяся символом NULL.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает указатель на место хранения для скопированной строки или значение `NULL`, если не удается выделить хранилище.  
  
## Заметки  
 Функция `_strdup` вызывает функцию [malloc](../../c-runtime-library/reference/malloc.md), которая выделяет пространство для хранения копии `strSource`, и копирует `strSource` в выделенное пространство.  
  
 Функции `_wcsdup` и `_mbsdup` являются версиями функции `_strdup` для расширенных и многобайтовых символов. Аргументы и возвращаемое значение `_wcsdup` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbsdup` представляют собой многобайтовые строки. В остальном эти три функции ведут себя идентично.  
  
### Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsdup`|`_strdup`|`_mbsdup`|`_wcsdup`|  
  
 Поскольку `_strdup` вызывает `malloc` для выделения пространства под копию `strSource`, рекомендуется освобождать соответствующую память, вызывая [свободную](../../c-runtime-library/reference/free.md) подпрограмму на указатель, возвращаемый вызовом функции `_strdup`.  
  
 Если определены директивы `_DEBUG` и `_CRTDBG_MAP_ALLOC`, вместо функций `_strdup` и `_wcsdup` вызываются функции `_strdup_dbg` и `_wcsdup_dbg`, что позволяет выполнить отладку выделения памяти. Для получения дополнительной информации см. [\_strdup\_dbg, \_wcsdup\_dbg](../Topic/_strdup_dbg,%20_wcsdup_dbg.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_strdup`|\<string.h\>|  
|`_wcsdup`|\<string.h\> или \<wchar.h\>|  
|`_mbsdup`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_strdup.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[] = "This is the buffer text";  
   char *newstring;  
   printf( "Original: %s\n", buffer );  
   newstring = _strdup( buffer );  
   printf( "Copy:     %s\n", newstring );  
   free( newstring );  
}  
```  
  
```Output  
Оригинал: это текст буфера Копия: это текст буфера  
```  
  
## Эквивалент в .NET Framework  
 [System::String::Clone](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)