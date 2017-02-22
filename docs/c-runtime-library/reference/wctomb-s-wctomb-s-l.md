---
title: "wctomb_s, _wctomb_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wctomb_s_l"
  - "wctomb_s"
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
  - "wctomb_s"
  - "_wctomb_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctomb_s_l - функция"
  - "знаки, преобразование"
  - "преобразование строк, многобайтовые строки символов"
  - "преобразование строк, расширенные символы"
  - "wctomb_s - функция"
  - "wctomb_s_l - функция"
  - "расширенные символы, преобразование"
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# wctomb_s, _wctomb_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует расширенный символ в соответствующий многобайтовый символ.  Это версия [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 \[исходящий\] `pRetValue`  
 Число байтов, или код, представляющий результат.  
  
 \[исходящий\] `mbchar`  
 Адрес многобайтового символа.  
  
 \[входящий\] `sizeInBytes`  
 Размер буфера `mbchar`.  
  
 \[входящий\] `wchar`  
 Расширенный символ.  
  
 \[входящий\] `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Нуль, если успешно; код ошибки при неудаче.  
  
 Условия возникновения ошибки  
  
|`mbchar`|`sizeInBytes`|Возвращаемое значение|`pRetValue`|  
|--------------|-------------------|---------------------------|-----------------|  
|`NULL`|\>0|`EINVAL`|без изменений|  
|any|\>`INT_MAX`|`EINVAL`|без изменений|  
|any|слишком мало|`EINVAL`|без изменений|  
  
 Если случается какая\-либо из выше перечисленных ошибок, то вызывается обработчик недопустимых параметров, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, то `wctomb` возвращает `EINVAL` и устанавливает `errno` в `EINVAL`.  
  
## Заметки  
 Функция `wctomb_s` преобразует свой аргумент `wchar` в соответствующие многобайтовые символы и сохраняет результат в `mbchar`.  Функцию можно вызвать из любого места в любой программе.  
  
 Если `wctomb_s` преобразует расширенный символ в многобайтовый символ, она помещает количество байтов \(которое никогда не превышает `MB_CUR_MAX`\) расширенного символа в целое число, указанное в `pRetValue`.  Если `wchar` расширенный нуль\-символ \(L'\\0\), `wctomb_s` помещает в `pRetValue` значение 1.  Если указатель на целевой объект `mbchar` равен NULL, `wctomb_s` помещает в `pRetValue` значение 0.  Если в текущем языковом стандарте преобразование невозможно, `wctomb_s` помещает в `pRetValue` значение \-1.  
  
 `wctomb_s` использует текущий языковой стандарт для сведений, зависящих от языкового стандарта; `_wctomb_s_l` идентична за исключением того, что она использует переданный языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`wctomb_s`|\<stdlib.h\>|  
|`_wctomb_s_l`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 Эта программа иллюстрирует поведение функции `wctomb`.  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
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