---
title: "_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l | Microsoft Docs"
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
  - "_mbcjistojms"
  - "_mbcjmstojis"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
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
  - "mbcjistojms"
  - "_mbcjistojms"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
  - "_mbcjmstojis"
  - "mbcjmstojis_l"
  - "mbcjistojms_l"
  - "mbcjmstojis"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbcjistojms - функция"
  - "_mbcjistojms_l - функция"
  - "_mbcjmstojis - функция"
  - "_mbcjmstojis_l - функция"
  - "mbcjistojms - функция"
  - "mbcjistojms_l - функция"
  - "mbcjmstojis - функция"
  - "mbcjmstojis_l - функция"
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проводит преобразование между символами JIS и символами JMS.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
unsigned int _mbcjistojms(  
   unsigned int c   
);  
unsigned int _mbcjistojms_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbcjmstojis(  
   unsigned int c   
);  
unsigned int _mbcjmstojis_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `c`  
 Преобразуемый символ.  
  
 `local`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 В японском языковом стандарте эти функции возвращают преобразованный символ или возвращают 0, если преобразование невозможно.  В не японском языковом стандарте эти функции возвращают переданный символ.  
  
## Заметки  
 Функция `_mbcjistojms`  преобразовывает символ JIS в символ Майкрософт Кандзи \(Shift JIS\).  Символ преобразовывает, только если старший и младший байты в диапазоне 0x21 — 0x7E.  Если старший или младший байты вне этого диапазона, `errno` принимает значение `EILSEQ`.  Дополнительные сведения об этом и других кодах ошибки см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 Функция `_mbcjmstojis`преобразует символ Shift JIS в символ JIS.  Символ преобразуется, только если старший байт в диапазоне от 0x81 до 0x9F или от 0xE0 до 0xFC, и младший байт в диапазоне от 0x40 до 0x7E или от 0x80 до 0xFC.  Обратите внимание, что некоторые кодовые точки в этом диапазоне не содержат присвоенный символ, и поэтому не могут быть преобразованы.  
  
 Значение `c` должно быть 16\-разрядным, старшие 8 бит которого представляют старший байт символа для преобразования и младшие 8 юит которого представляют его младший байт.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В более ранних версиях, `_mbcjistojms` и `_mbcjmstojis` назывались `jistojms` и `jmstojis` соответственно.  Вместо них следует использовать `_mbcjistojms`,`_mbcjistojms_l`,`_mbcjmstojis` и `_mbcjmstojis_l`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_mbcjistojms`|\<mbstring.h\>|  
|`_mbcjistojms_l`|\<mbstring.h\>|  
|`_mbcjmstojis`|\<mbstring.h\>|  
|`_mbcjmstojis_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Процедуры \_ismbb](../../c-runtime-library/ismbb-routines.md)