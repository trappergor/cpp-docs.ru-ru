---
title: "_mbbtype, _mbbtype_l | Microsoft Docs"
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
  - "_mbbtype"
  - "_mbbtype_l"
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
  - "_mbbtype_l"
  - "mbbtype"
  - "mbbtype_l"
  - "_mbbtype"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbbtype - функция"
  - "_mbbtype_l - функция"
  - "mbbtype - функция"
  - "mbbtype_l - функция"
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbbtype, _mbbtype_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает тип байта, основываясь на предыдущем байте.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _mbbtype(  
   unsigned char c,  
   int type   
);  
int _mbbtype_l(  
   unsigned char c,  
   int type,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `c`  
 Проверяемый символ.  
  
 `type`  
 Тип байта для проверки.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 `_mbbtype` возвращает тип байта в строке.  Это решение контекстно зависимо — на это указывает значение параметра `type`, который определяет условие проверки управления.  `type` — это тип предыдущего байта в строку.  Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.  
  
|Значение `type`|`_mbbtype` Тестируемые наборы символов|Возвращаемое значение|`c`|  
|---------------------|--------------------------------------------|---------------------------|---------|  
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|`_MBC_SINGLE` \(0\)|Одиночный байт \(0x20–0x7E, 0xA1–0xDF\)|  
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|`_MBC_LEAD` \(1\)|Старший байт многобайтового символа \(0x81–0x9F, 0xE0–0xFC\)|  
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|`_MBC_ILLEGAL`<br /><br /> \( –1\)|Недопустимый символ \(любое значение, кроме 0x20–0x7E, 0xA1–0xDF, 0x81–0x9F, 0xE0–0xFC\)|  
|1|Допустимый младший байт|`_MBC_TRAIL` \(2\)|Конечный байт многобайтового символа \(0x40–0x7E, 0x80–0xFC\)|  
|1|Допустимый младший байт|`_MBC_ILLEGAL`<br /><br /> \( –1\)|Недопустимый символ \(любое значение, кроме 0x20–0x7E, 0xA1–0xDF, 0x81–0x9F, 0xE0–0xFC\)|  
  
## Заметки  
 Функция `_mbbtype` определяет тип байта в многобайтовом символе.  Если параметр `type` имеет любым значение, кроме 1, `_mbbtype` проверяет допустимый одиночный байт или старший байт многобайтового символа.  Если значение параметра `type` равно 1, `_mbbtype` проверяет допустимый младший байт многобайтового символа.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Версия `_mbbtype` этой функции использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; версия `_mbbtype_l` работает аналогично, но использует переданный языковой стандарт.  Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В более ранних версиях функция `_mbbtype` называлась `chkctype`.  Для нового кода используйте вместо нее `_mbbtype`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_mbbtype`|\<mbstring.h\>|\<mbctype.h\>\*|  
|`_mbbtype_l`|\<mbstring.h\>|\<mbctype.h\>\*|  
  
 \* Для определения констант манифеста, которые используются в качестве возвращаемых значений.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).  
  
## См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)