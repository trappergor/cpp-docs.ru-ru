---
title: "wctomb, _wctomb_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wctomb_l"
  - "wctomb"
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
  - "wctomb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctomb_l - функция"
  - "знаки, преобразование"
  - "преобразование строк, многобайтовые строки символов"
  - "преобразование строк, расширенные символы"
  - "wctomb - функция"
  - "wctomb_l - функция"
  - "расширенные символы, преобразование"
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# wctomb, _wctomb_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует расширенный символ в соответствующий многобайтовый символ.  Существуют более безопасные версии этих функций; см. раздел [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md).  
  
## Синтаксис  
  
```  
int wctomb(  
   char *mbchar,  
   wchar_t wchar   
);  
int _wctomb_l(  
   char *mbchar,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `mbchar`  
 Адрес многобайтового символа.  
  
 `wchar`  
 Расширенный символ.  
  
## Возвращаемое значение  
 Если `wctomb` преобразует расширенный символ в многобайтовые, возвращается число байтов \(которое никогда не больше, чем `MB_CUR_MAX`\) в расширенном символе.  Если `wchar` расширенный нулевой символ \(L'\\0\), `wctomb` возвращает 1.  Если указатель назначения `mbchar` является NULL, `wctomb` возвращает 0.  Если преобразование невозможно для текущего языкового стандарта, `wctomb` возвращает –1, и `errno` устанавливается в `EILSEQ`.  
  
## Заметки  
 Функция `wctomb` преобразует свой аргумент `wchar` в соответствующие многобайтовые символы и сохраняет результат в `mbchar`.  Функцию можно вызвать из любого места в любой программе.  `wctomb` использует текущий языковой стандарт для операций, зависящих от языкового стандарта; `_wctomb_l` идентична `wctomb` за исключением того, что она использует переданный ей языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 `wctomb` проверяет свои параметры.  Если параметр `mbchar` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, `errno` принимает значение `EINVAL`, и функция возвращает \-1.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`wctomb`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 Эта программа иллюстрирует поведение функции wctomb.  
  
```  
// crt_wctomb.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int i;  
   wchar_t wc = L'a';  
   char *pmb = (char *)malloc( MB_CUR_MAX );  
  
   printf( "Convert a wide character:\n" );  
   i = wctomb( pmb, wc ); // C4996  
   // Note: wctomb is deprecated; consider using wctomb_s  
   printf( "   Characters converted: %u\n", i );  
   printf( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
  **Convert a wide character:**  
 **Characters converted: 1**  
 **Multibyte character: a**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)   
 [wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)