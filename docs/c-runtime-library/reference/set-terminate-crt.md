---
title: "set_terminate (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "set_terminate"
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
  - "set_terminate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка исключений, завершение"
  - "set_terminate - функция"
  - "terminate - функция"
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# set_terminate (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Устанавливает собственную процедуру завершения, чтобы ее можно было вызвать с помощью `terminate`.  
  
## Синтаксис  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### Параметры  
 `termFunction`  
 Указатель на написанную функцию завершения.  
  
## Возвращаемое значение  
 Возвращает указатель на предыдущую функцию, зарегистрированную `set_terminate`, чтобы предыдущую функцию можно было впоследствии восстановить.  Если предыдущая функция не задана, то возвращаемое значение может использоваться для восстановления поведения по умолчанию; это значение может быть равно NULL.  
  
## Заметки  
 Функция `set_terminate` устанавливает `termFunction` как функцию, вызываемую `terminate`.  `set_terminate` используется с обработкой исключений C\+\+ и может быть вызвана в любой момент в программе до возникновения исключения.  По умолчанию `terminate` вызывает `abort`.  Можно изменить эту реакцию по умолчанию, создав собственную функцию завершения и вызвав `set_terminate` с именем этой функции в качестве аргумента.  `terminate` вызывает последнюю функцию, заданную в качестве аргумента для `set_terminate`.  После выполнения всех необходимых задач очистки, `termFunction` должна завершить программу.  Если она не завершает \(если она возвращается к вызывавшему объекту\), вызывается `abort`.  
  
 В многопотоковой среде функции завершения поддерживаются отдельно для каждого потока.  Каждый новый поток требует установки собственной функции завершения.  Таким образом, каждый поток владеет собственной обработкой завершения.  
  
 Тип `terminate_function` определен в EH.H в качестве указателя на определенную пользователем функцию завершения, `termFunction`, возвращающую `void`.  Пользовательская функция `termFunction` может не иметь аргументов и не должна возвращаться к вызывавшему ее объекту.  Если она возвращает значение, вызывается `abort`.  Исключение не может быть создано в `termFunction`.  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  Функция `set_terminate` работает только вне отладчика.  
  
 Существует один обработчик `set_terminate` для всех динамически связанных DLL или EXE; даже при вызове `set_terminate` обработчик может быть заменен другим или можно заменить обработчик с помощью других DLL или EXE.  
  
 Эта функция не поддерживается в **\/clr:pure**.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`set_terminate`|\<eh.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [terminate](../../c-runtime-library/reference/terminate-crt.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../Topic/unexpected%20\(CRT\).md)