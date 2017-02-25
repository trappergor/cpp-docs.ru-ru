---
title: "_mbsnbcat, _mbsnbcat_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbcat_l"
  - "_mbsnbcat"
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
  - "mbsnbcat"
  - "mbsnbcat_l"
  - "_mbsnbcat"
  - "_mbsnbcat_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcat - функция"
  - "_mbsnbcat_l - функция"
  - "_tcsncat - функция"
  - "_tcsncat_l - функция"
  - "mbsnbcat - функция"
  - "mbsnbcat_l - функция"
  - "tcsncat - функция"
  - "tcsncat_l - функция"
ms.assetid: aa0f1d30-0ddd-48d1-88eb-c6884b20fd91
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# _mbsnbcat, _mbsnbcat_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Добавляет максимум `n` первых байтов одной многобайтовой строки к другой.  Существуют более безопасные версии этих функций; см. раздел [\_mbsnbcat\_s, \_mbsnbcat\_s\_l](../Topic/_mbsnbcat_s,%20_mbsnbcat_s_l.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
unsigned char *_mbsnbcat(  
   unsigned char *dest,  
   const unsigned char *src,  
   size_t count   
);  
unsigned char *_mbsnbcat_l(  
   unsigned char *dest,  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
unsigned char *_mbsnbcat(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count   
); // C++ only  
template <size_t size>  
unsigned char *_mbsnbcat_l(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 `dest`  
 Завершаемая нулевым символом многобайтовая строка назначения.  
  
 `src`  
 Завершаемая нулевым символом исходная многобайтовая строка.  
  
 `count`  
 Число байтов из `src`, добавляемых к `dest`.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 `_mbsnbcat` возвращает указатель на строку назначения.  Нет зарезервированных возвращаемых значений для указания ошибки.  
  
## Заметки  
 Функция `_mbsnbcat` добавляет в `dest` не более `count` первых байтов из `src`.  Если байт непосредственно перед нулевым символом в `dest` является старшим байтом, он перезаписывается начальным байтом `src`.  В противном случае начальный байт `src` перезапишет завершающий нулевой символ `dest`.  Если нулевой байт возникает в `src` прежде, чем добавлено `count` байтов, \_`mbsnbcat` добавляет все байты из `src` вплоть до нулевого символа.  Если `count` больше, чем длина `src`, длина `src` используется вместо `count`.  Результирующая строка завершается нулевым символом.  Если копирование производится между перекрывающимися строками, поведение не определено.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версия `_mbsnbcat` использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; `_mbsnbcat_l` идентична, за исключением того, что использует переданный языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 **Примечание о безопасности** Следует использовать строку, оканчивающуюся символом null.  Завершающаяся нулевым символом строка не должна превышать размер буфера назначения.  Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Если `dest` или `src` — `NULL`, функция создаст ошибку недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если ошибка обработана, функция возвращает `EINVAL` и устанавливает `errno` в `EINVAL`.  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsncat`|[strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|`_mbsnbcat`|[wcsncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|  
|`_tcsncat_l`|`_strncat_l`|`_mbsnbcat_l`|`_wcsncat_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_mbsnbcat`|\<mbstring.h\>|  
|`_mbsnbcat_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_strncnt, \_wcsncnt, \_mbsnbcnt, \_mbsnbcnt\_l, \_mbsnccnt, \_mbsnccnt\_l](../Topic/_strncnt,%20_wcsncnt,%20_mbsnbcnt,%20_mbsnbcnt_l,%20_mbsnccnt,%20_mbsnccnt_l.md)   
 [\_mbsnbcpy, \_mbsnbcpy\_l](../Topic/_mbsnbcpy,%20_mbsnbcpy_l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [\_mbsnbcat\_s, \_mbsnbcat\_s\_l](../Topic/_mbsnbcat_s,%20_mbsnbcat_s_l.md)