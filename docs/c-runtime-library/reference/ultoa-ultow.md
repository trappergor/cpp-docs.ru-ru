---
title: "_ultoa, _ultow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ultoa"
  - "_ultow"
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
  - "ultot"
  - "ultow"
  - "_ultoa"
  - "_ultow"
  - "_ultot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ultoa - функция"
  - "_ultot - функция"
  - "_ultow - функция"
  - "преобразование целых чисел"
  - "преобразование чисел, к строкам"
  - "целые числа, преобразование"
  - "ultot - функция"
  - "ultow - функция"
ms.assetid: 7a472dc4-5652-4513-93c3-3358522c23be
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _ultoa, _ultow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразовывают unsigned long integer в строку.  Существуют более безопасные версии этих функций; см. раздел [\_ultoa\_s, \_ultow\_s](../Topic/_ultoa_s,%20_ultow_s.md).  
  
## Синтаксис  
  
```  
char *_ultoa(  
   unsigned long value,  
   char *str,  
   int radix   
);  
wchar_t *_ultow(  
   unsigned long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ultoa(  
   unsigned long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ultow(  
   unsigned long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### Параметры  
 `value`  
 Число, которое нужно преобразовать.  
  
 `str`  
 Строковый результат.  
  
 `radix`  
 Основание системы счисления для `value`*.*  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает указатель на `str`.  Нет какого\-либо возврата ошибки.  
  
## Заметки  
 Функция `_ultoa` преобразует `value` в символьную строку, завершающуюся символом null, и сохраняет результат \(до 33 байт\) в `str`.  Проверка на переполнение не выполняется.  `radix` определяет основание системы счисления `value`; `radix` должно находиться в диапазоне от 2 до 36.  `_ultow` — это версия `_ultoa` для расширенных символов.  
  
> [!IMPORTANT]
>  Чтобы предотвратить переполнение буфера, убедитесь, что буфер `str` достаточно велик для хранения преобразованных цифр, а также конечного символа null.  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_ultot`|`_ultoa`|`_ultoa`|`_ultow`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_ultoa`|\<stdlib.h\>|  
|`_ultow`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [\_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md).  
  
## Эквивалент в .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)