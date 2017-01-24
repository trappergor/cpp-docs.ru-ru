---
title: "_set_abort_behavior | Microsoft Docs"
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
  - "_set_abort_behavior"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_abort_behavior"
  - "set_abort_behavior"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_abort_behavior - функция"
  - "прерывание программ"
  - "set_abort_behavior - функция"
ms.assetid: 43918766-e4ba-4b1f-80e8-1a4a910cd452
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_abort_behavior
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает действие, которое необходимо выполнить, если программа ненормально завершена.  
  
> [!NOTE]
>  Не используйте функцию `abort` для завершения приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], за исключением сценариев тестирования или отладки.  Закрытие приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] программным способом или с помощью пользовательского интерфейса на допускается в соответствии с разделом 3.6 [сертификационных требований к приложениям для Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889).  Дополнительные сведения см. в разделе [Жизненный цикл приложения \(приложения Магазина Windows\)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Синтаксис  
  
```  
unsigned int _set_abort_behavior(  
   unsigned int flags,  
   unsigned int mask  
);  
```  
  
#### Параметры  
 \[входящий\] `flags`  
 Новое значение флагов `abort`.  
  
 \[входящий\] `mask`  
 Маска для задаваемых битов флагов `abort`.  
  
## Возвращаемое значение  
 Прежнее значение флагов.  
  
## Заметки  
 Существует два флага `abort`: `_WRITE_ABORT_MSG` и `_CALL_REPORTFAULT`.  `_WRITE_ABORT_MSG` определяет, выводится ли вспомогательное сообщение при аварийном завершении программы.  Сообщение заявляет, что приложение вызывает функцию `abort`.  Реакция на событие по умолчанию — печать сообщения.  `_CALL_REPORTFAULT`, если задано, определяет, что создается и передается аварийный дамп Уотсона при вызове `abort`.  По умолчанию создание отчетов с аварийным дампом в неотладочных сборках включено.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_set_abort_behavior`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```c  
// crt_set_abort_behavior.c  
// compile with: /TC  
#include <stdlib.h>  
  
int main()  
{  
   printf("Suppressing the abort message. If successful, this message"  
          " will be the only output.\n");  
   // Suppress the abort message  
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);  
   abort();  
}  
```  
  
  **Подавление сообщения прерывания.  В случае успеха это сообщение является единственными выходными данными.**    
## См. также  
 [abort](../../c-runtime-library/reference/abort.md)