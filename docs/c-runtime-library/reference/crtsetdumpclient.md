---
title: "_CrtSetDumpClient | Microsoft Docs"
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
  - "_CrtSetDumpClient"
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
  - "_CrtSetDumpClient"
  - "CrtSetDumpClient"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtSetDumpClient - функция"
  - "CrtSetDumpClient - функция"
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetDumpClient
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Устанавливает определенную приложением функцию, чтобы сбросить в дамп блоки памяти типа `_CLIENT_BLOCK` \(только для отладочной версии\).  
  
## Синтаксис  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### Параметры  
 `dumpClient`  
 Новая, определенная клиентом функция дампа для внедрения в процесс дампа отладочной памяти среды выполнения C.  
  
## Возвращаемое значение  
 Возвращает ранее определенную функцию дампа блока клиента.  
  
## Заметки  
 Функция `_CrtSetDumpClient` позволяет приложению перехватить собственную функцию дампа объектов, хранящихся в виде блоков памяти `_CLIENT_BLOCK` в процессе дампа отладочной памяти среды выполнения C.  В результате, каждый раз, когда функция отладочного дампа, например, [\_CrtMemDumpAllObjectsSince](../Topic/_CrtMemDumpAllObjectsSince.md) или [\_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) сбрасывает блок памяти `_CLIENT_BLOCK`, также вызывается функция дампа приложения.  `_CrtSetDumpClient` предоставляет приложение с простым методом для обнаружения утечек памяти и проверки или информировании о содержимом данных, хранящихся в блоках `_CLIENT_BLOCK`.  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, то вызовы `_CrtSetDumpClient` удаляются во время предварительной обработки.  
  
 Функция `_CrtSetDumpClient` устанавливает новую, определенную приложением функцию дампа, указанную в `dumpClient`, и возвращает ранее определенную функцию дампа.  Пример функции дампа клиентского блока выглядит следующим образом:  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 Аргумент `userPortion` является указателем на начало части пользовательских данных блоков памяти, а `blockSize` определяет размер выделенных блоков памяти в байтах.  Функция дампа клиентского блока должна возвращать `void`.  Указатель на функцию дампа клиентского блока, который передается `_CrtSetDumpClient`, имеет тип `_CRT_DUMP_CLIENT`, как определено в Crtdbg.h:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 Дополнительные сведения о функциях, работающих с блоками памяти типа `_CLIENT_BLOCK`, см. раздел [Функции\-ловушки клиентского блока](../Topic/Client%20Block%20Hook%20Functions.md).  Функцию [\_CrtReportBlockType](../Topic/_CrtReportBlockType.md) можно использовать для получения сведений о типах и подтипах блоков.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtSetDumpClient`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [Библиотеки времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [\_CrtReportBlockType](../Topic/_CrtReportBlockType.md)   
 [\_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)