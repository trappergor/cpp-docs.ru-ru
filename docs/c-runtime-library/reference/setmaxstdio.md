---
title: "_setmaxstdio | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setmaxstdio"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "setmaxstdio"
  - "_setmaxstdio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setmaxstdio - функция"
  - "максимальное число открытых файлов"
  - "открыть файлы, максимум"
  - "setmaxstdio - функция"
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _setmaxstdio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает максимальное число одновременно открытых файлов на уровне `stdio`.  
  
## Синтаксис  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### Параметры  
 `newmax`  
 Новое максимальное число одновременно открытых файлов на уровне `stdio`.  
  
## Возвращаемое значение  
 Возвращает значение `newmax` в случае успешного выполнения; в противном случае — значение –1.  
  
 Если `newmax` меньше, чем `_IOB_ENTRIES` или больше, чем максимальное количество дескрипторов, доступных в операционной системе, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает \-1 и устанавливает `errno` в `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_setmaxstdio` изменяет максимальное число файлов, которые могут быть одновременно открыты на уровне `stdio`.  
  
 Ввод\-вывод среды выполнения C теперь поддерживает гораздо больше открытых файлов на платформах Win32, чем в предыдущих версиях.  До 2048 файлов могут быть открыты одновременно на [уровне lowio](../../c-runtime-library/low-level-i-o.md) \(то есть, открыты и доступны посредством `_open`, `_read`, `_write` и т.п. из семейства функций ввода\-вывода\).  До 512 файлов могут быть открыты одновременно на [уровне stdio](../../c-runtime-library/stream-i-o.md) \(то есть, открыты и доступны посредством `fopen`, `fgetc`, `fputc` и т.п. из семейства функций ввода\-вывода\).  Ограничение открытия 512 файлов на уровне `stdio` можно увеличить до 2048 с помощью функции `_setmaxstdio`.  
  
 Поскольку функции уровня `stdio`, например, `fopen`, строятся поверх функций `lowio`, максимум в 2048 файлов является жестким верхним пределом для числа одновременно открытых файлов, полученных через библиотеку времени выполнения C.  
  
> [!NOTE]
>  Этот верхний предел может оказаться выше того, что поддерживается конкретной платформой и конфигурацией Win32.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_setmaxstdio`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 Пример использования `_setmaxstdio` см. в [\_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)