---
title: "_CrtIsValidPointer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtIsValidPointer"
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
  - "CrtlsValidPointer"
  - "_CrtIsValidPointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtIsValidPointer - функция"
  - "CrtIsValidPointer - функция"
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _CrtIsValidPointer
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет, не равен ли указатель нулю.  В версиях библиотеки времени выполнения языка C, выпущенных до выхода Visual Studio 2010, проверяет, является ли указанный диапазон памяти допустимым для чтения и записи \(только отладочная версия\).  
  
## Синтаксис  
  
```  
int _CrtIsValidPointer(   
   const void *address,  
   unsigned int size,  
   int access   
);  
```  
  
#### Параметры  
 адрес  
 Указывает начало диапазона памяти для проверки.  
  
 `size`  
 Размер указанного диапазона памяти \(в байтах\).  
  
 access  
 Доступ на чтение или запись для определения диапазона памяти.  
  
## Возвращаемое значение  
 Оператор `_CrtIsValidPointer` возвращает значение TRUE, если указатель не равен нулю.  В версиях библиотеки CRT, выпущенных до выхода Visual Studio 2010, возвращает значение TRUE, если диапазон памяти допустим для указанной операции или операций.  В противном случае функция возвращает значение FALSE.  
  
## Заметки  
 Начиная с версии библиотеки CRT в составе Visual Studio 2010, параметры размера и доступа не учитываются, а `_CrtIsValidPointer` следит только за тем, чтобы указанный адрес не был пустым.  Поскольку этот тест легко выполняется вручную, не рекомендуем использовать данную функцию.  В версиях, выпущенных до выхода Visual Studio 2010, эта функция проверяет допустимость диапазона памяти, начинающегося по адресу `address` и занимающего заданное параметром `size` количество байт, для указанной операции или операций доступа.  Если для параметра `access` задано значение TRUE, диапазон памяти проверяется для обеих операций: чтения и записи.  Если значение параметра `access` — FALSE, проверяется допустимость диапазона памяти только для чтения.  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, вызовы `_CrtIsValidPointer` удаляются на этапе предварительной обработки.  
  
 Поскольку эта функция возвращает значение TRUE или FALSE, ее можно передать в один из макросов [\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) для создания простого механизма обработки ошибок отладки.  Следующий пример вызывает сбой утверждения, если диапазон памяти недопустим для операций чтения и записи.  
  
```  
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );  
```  
  
 Дополнительные сведения о том, как использовать `_CrtIsValidPointer` с другими функциями и макросами отладки, см. в статье [Макросы для создания отчетов](../Topic/Macros%20for%20Reporting.md).  Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии основной кучи см. в статье [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtIsValidPointer`|\<crtdbg.h\>|  
  
 `_CrtIsValidPointer` является расширением Майкрософт.  Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
 См. пример для раздела [\_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)