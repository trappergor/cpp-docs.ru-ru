---
title: "_mbsnbcpy_s, _mbsnbcpy_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbcpy_s_l"
  - "_mbsnbcpy_s"
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
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbcpy_s_l"
  - "_mbsnbcpy_s"
  - "mbsnbcpy_s"
  - "_mbsnbcpy_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcpy_s - функция"
  - "_mbsnbcpy_s_l - функция"
  - "_tcsncpy_s - функция"
  - "_tcsncpy_s_l - функция"
  - "mbsnbcpy_s - функция"
  - "mbsnbcpy_s_l - функция"
  - "tcsncpy_s - функция"
  - "tcsncpy_s_l - функция"
ms.assetid: dfff64ab-fe6f-49c4-99ba-75014e2b0cd6
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# _mbsnbcpy_s, _mbsnbcpy_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Копирует `n` байт строки в строку назначения.  В этих версиях [\_mbsnbcpy, \_mbsnbcpy\_l](../Topic/_mbsnbcpy,%20_mbsnbcpy_l.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
errno_t _mbsnbcpy_s(  
   unsigned char * strDest,  
   size_t sizeInBytes,  
   const unsigned char * strSource,  
   size_t count   
);  
errno_t _mbsnbcpy_s_l(  
   unsigned char * strDest,  
   size_t sizeInBytes,  
   const unsigned char * strSource,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _mbsnbcpy_s(  
   unsigned char (&strDest)[size],  
   const unsigned char * strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsnbcpy_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char * strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 `strDest`  
 Назначение для копирования символьной строки.  
  
 `sizeInBytes`  
 Размер буфера назначения.  
  
 `strSource`  
 Копируемая строка символов.  
  
 `count`  
 Число байтов для копирования.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Ноль в случае успешного завершения; `EINVAL`, если был передан недопустимый параметр.  
  
## Заметки  
 Функция `_mbsnbcpy_s` копирует `count` байт из `strSource` в `strDest`.  Если `count` превышает размер `strDest`, или любая из входных строк \- указатель на null, или либо `sizeInBytes`, либо `count` равно 0, то функция вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает `EINVAL`.  При перекрытии исходной и конечной строк поведение `_mbsnbcpy_s` не определено.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  В отличие от небезопасной версии этой функции, `_mbsnbcpy_s` не производит вставку null и всегда завершает строку нуль\-символом.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD.  Для отключения данного поведения используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsncpy_s`|`_strncpy_s`|`_mbsnbcpy_s`|`_wcsncpy_s`|  
|`_tcsncpy_s_l`|`_strncpy_s_l`|`_mbsnbcpy_s_l`|`_wcsncpy_s_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_mbsnbcpy_s`|\<mbstring.h\>|  
|`_mbsnbcpy_s_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_strncnt, \_wcsncnt, \_mbsnbcnt, \_mbsnbcnt\_l, \_mbsnccnt, \_mbsnccnt\_l](../Topic/_strncnt,%20_wcsncnt,%20_mbsnbcnt,%20_mbsnbcnt_l,%20_mbsnccnt,%20_mbsnccnt_l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)