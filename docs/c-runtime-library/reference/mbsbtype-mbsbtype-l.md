---
title: "_mbsbtype, _mbsbtype_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsbtype_l"
  - "_mbsbtype"
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
  - "mbsbtype"
  - "mbsbtype_l"
  - "_mbsbtype_l"
  - "_mbsbtype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsbtype - функция"
  - "_mbsbtype_l - функция"
  - "mbsbtype - функция"
  - "mbsbtype_l - функция"
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _mbsbtype, _mbsbtype_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает тип байта внутри строки.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _mbsbtype(  
   const unsigned char *mbstr,  
   size_t count   
);  
int _mbsbtype_l(  
   const unsigned char *mbstr,  
   size_t count,  
   _locale_t locale   
);  
```  
  
#### Параметры  
 `mbstr`  
 Адрес последовательности многобайтовых символов.  
  
 `count`  
 Смещение в байтах от начала строки.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 `_mbsbtype` и `_mbsbtype_l`возвращают целочисленное значение, представляющее результат для указанного байта.  Константы манифеста из следующей таблицы определены в Mbctype.h.  
  
|Возвращаемое значение|Тип байтов|  
|---------------------------|----------------|  
|`_MBC_SINGLE` \(0\)|Одиночный символ  Например, в кодовой странице 932 `_mbsbtype` возвращает 0, если указанный байт в диапазоне 0x20 \- 0x7E или 0xA1 \- 0xDF.|  
|`_MBC_LEAD` \(1\)|Старший байт многобайтового символа.  Например, в кодовой странице 932 `_mbsbtype` возвращает 1, если указанный байт в диапазоне 0x81 – 0x9F или 0xE0 – 0xFC.|  
|`_MBC_TRAIL` \(2\)|Конечный байт многобайтового символа.  Например, в кодовой странице 932 `_mbsbtype` возвращает 2, если указанный байт в диапазоне 0x40 – 0x7E или 0x80 – 0xFC.|  
|`_MBC_ILLEGAL` \(–1\)|Пустая строка \(`NULL`\), недопустимый символ или пустой байт \(`NULL`\) найдены перед байтом со смещением `count` в `mbstr`.|  
  
## Заметки  
 Функция `_mbsbtype` определяет тип байта в строке многобайтовых символов.  Функция проверяет только байт по смещению `count` в `mbstr`, игнорируя недопустимые символы перед указанным байтом.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версия этой функции без суффикса `_l` использует текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версия с суффиксом `_l` идентична, за исключением того, что она использует переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если входная строка имеет значение `NULL`, то вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, то `errno` устанавливается в `EINVAL`, и функция возвращает `_MBC_ILLEGAL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_mbsbtype`|\<mbstring.h\>|\<mbctype.h\>\*|  
|`_mbsbtype_l`|\<mbstring.h\>|\<mbctype.h\>\*|  
  
 \* Для констант манифеста, используемых в качестве возвращаемых значений.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).  
  
## См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)