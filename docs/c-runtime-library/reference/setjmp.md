---
title: "setjmp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setjmp"
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
  - "setjmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "программы [C++], сохранение состояний"
  - "текущее состояние"
  - "Функция setjmp"
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# setjmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сохраняет текущее состояние программы.  
  
## Синтаксис  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### Параметры  
 `env`  
 Переменная для хранения среды.  
  
## Возвращаемое значение  
 Возвращает 0 после сохранения среды стека.  Если `setjmp` возвращается в результате вызова `longjmp`, она возвращает аргумент `value` функции `longjmp`, или если аргумент `value` функции `longjmp` равен 0, `setjmp` возвращает 1.  Нет какого\-либо возврата ошибки.  
  
## Заметки  
 Функция `setjmp` сохраняет среду стека, которую можно впоследствии восстановить с помощью `longjmp`.  Когда `setjmp` и `longjmp` используются вместе, они предоставляют способ выполнения нелокального `goto`.  Обычно они используются для передачи управления выполнением в код обработки ошибок или восстановления в вызванной ранее подпрограмме без использования обычных соглашений вызова или возврата.  
  
 Вызов `setjmp` сохраняет текущую среду стека в `env`.  Последующий вызов `longjmp` восстанавливает сохраненную среду и возвращает контроль управления в точку, следующей сразу за соответствующим вызовом `setjmp`.  Все переменные \(за исключением переменных регистра\), доступные для получившей контроль управления подпрограммы, содержат те значения, которые они имели при вызове `longjmp`.  
  
 Невозможно использовать `setjmp`, чтобы перейти из машинного кода в управляемый.  
  
 **Бумага для заметок** `setjmp` и `longjmp` не поддерживают семантики объекта C\+\+.  В программах на C\+\+ используйте механизм обработки исключений C\+\+.  
  
 Дополнительные сведения см. в разделе [Использование setjmp и longjmp](../../cpp/using-setjmp-longjmp.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`setjmp`|\<setjmp.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 Посмотрите следующий пример для [\_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [\_setjmp3](../../c-runtime-library/setjmp3.md)