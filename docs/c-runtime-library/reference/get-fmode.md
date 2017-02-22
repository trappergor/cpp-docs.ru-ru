---
title: "_get_fmode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_fmode"
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
  - "get_fmode"
  - "_get_fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_fmode - функция"
  - "перевод файла [C++], режим по умолчанию"
  - "get_fmode - функция"
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _get_fmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает режим преобразования файла по умолчанию для операций файлового ввода\-вывода.  
  
## Синтаксис  
  
```  
errno_t _get_fmode(   
   int * pmode   
);  
```  
  
#### Параметры  
 \[исходящий\] `pmode`  
 Указатель на целое число для заполнения текущим режимом по умолчанию: `_O_TEXT` или `_O_BINARY`.  
  
## Возвращаемое значение  
 Возвращает ноль в случае успеха; код ошибки при неудаче.  Если параметр `pmode` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, то `errno` устанавливается в `EINVAL`, и функция возвращает `EINVAL`.  
  
## Заметки  
 Функция получает значения глобальной переменной [\_fmode](../../c-runtime-library/fmode.md).  Эта переменная указывает режим преобразования файла по умолчанию для операций потокового и низкоуровневого файлового ввода\-вывода, например `_open`, `_pipe`, `fopen` и `freopen`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_get_fmode`|\<stdlib.h\>|\<fcntl.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример в разделе [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [\_fmode](../../c-runtime-library/fmode.md)   
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [Файловый ввод\-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md)