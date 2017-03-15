---
title: "_ltoa_s, _ltow_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ltoa_s"
  - "_ltow_s"
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
apitype: "DLLExport"
f1_keywords: 
  - "_ltow_s"
  - "_ltoa_s"
  - "ltoa_s"
  - "ltow_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ltoa_s - функция"
  - "_ltow_s - функция"
  - "преобразование целых чисел"
  - "преобразование чисел, к строкам"
  - "преобразование длинного целого в строку"
  - "ltoa_s - функция"
  - "ltow_s - функция"
ms.assetid: d7dc61ea-1ccd-412d-b262-555a58647386
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _ltoa_s, _ltow_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует целое число типа long в строку.  Здесь представлены версии [\_ltoa, \_ltow](../Topic/_ltoa,%20_ltow.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _ltoa_s(  
    long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ltow_s(  
    long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ltoa_s(  
    long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ltow_s(  
    long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### Параметры  
 `value`  
 Число, которое нужно преобразовать.  
  
 `str`  
 Буфер для результирующей строки.  
  
 `sizeOfstr`  
 Размер `str` в байтах для `_ltoa_s` или словах для `_ltow_s`.  
  
 `radix`  
 Основание системы счисления для `value`.  
  
## Возвращаемое значение  
 Ноль, если функция завершилась успешно, или код ошибки.  
  
## Заметки  
 Функция `_ltoa_s` преобразует цифры `value` в строку знаков, завершающуюся значением null, и сохраняет результат \(до 33 байт\) в `str`.  Аргумент `radix` определяет основание системы счисления `value`, которое должно быть в диапазоне от 2 до 36.  Если `radix` равно 10 и `value` имеет отрицательное значение, то первым символом результирующей строки будет знак "минус" \(–\).  `_ltow_s` — это версия `_ltoa_s` для расширенных символов; второй аргумент функции `_ltow_s` представляет собой строки расширенных символов.  
  
 Если `str` равен `NULL` или `sizeOfstr` меньше или равно нулю, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают \-1 и устанавливают `errno` в `EINVAL` , или если `value` или `str` вне диапазона длинного целого числа, эти функции возвращают \-1 и устанавливают `errno` в `ERANGE`.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_ltot_s`|`_ltoa_s`|`_ltoa_s`|`_ltow_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_ltoa_s`|\<stdlib.h\>|  
|`_ltow_s`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [\_ultoa\_s, \_ultow\_s](../Topic/_ultoa_s,%20_ultow_s.md)