---
title: "set_unexpected (CRT) | Microsoft Docs"
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
  - "set_unexpected"
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
  - "set_unexpected"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "обработка исключений, завершение"
  - "set_unexpected - функция"
  - "неожиданная функция"
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# set_unexpected (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Устанавливает вашу собственную завершающую функцию, которая будет вызываться `unexpected`.  
  
## Синтаксис  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### Параметры  
 `unexpFunction`  
 Указатель на функцию, написанную для замены функции `unexpected`.  
  
## Возвращаемое значение  
 Возвращает указатель на предыдущую завершающую функцию, зарегистрированную `_set_unexpected`, чтобы предыдущую функцию можно было впоследствии восстановить.  Если предыдущая функция не задана, то возвращаемое значение может использоваться для восстановления поведения по умолчанию; это значение может быть равно NULL.  
  
## Заметки  
 Функция `set_unexpected` устанавливает `unexpFunction` как функцию, вызываемую `unexpected`.  `unexpected` не используется в текущей реализации обработки исключений C\+\+.  Тип `unexpected_function` определен в EH.H в качестве указателя на определенную пользователем неожиданную функцию, `unexpFunction`, возвращающую `void`.  Пользовательская функция `unexpFunction` не должна возвращаться к вызывающему объекту.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 По умолчанию `unexpected` вызывает `terminate`.  Можно изменить это поведение по умолчанию, создав собственную функцию завершения и вызвав `set_unexpected` с именем этой функции в качестве аргумента.  `unexpected` вызывает последнюю функцию, заданную в качестве аргумента для `set_unexpected`.  
  
 В отличие от пользовательских функций завершения, установленных с помощью вызова `set_terminate`, исключение можно вызывать из `unexpFunction`.  
  
 В многопотоковой среде неожиданные функции поддерживаются отдельно для каждого потока.  Каждый новый поток требует установки собственной неожиданной функции.  Таким образом, каждый поток владеет собственной обработкой неожиданных ситуаций.  
  
 В текущей реализации обработки исключений C\+\+ от Майкрософт `unexpected` вызывает `terminate` по умолчанию и никогда не вызывается библиотекой обработки исключений времени выполнения.  Нет каких\-либо преимуществ в вызове `unexpected` вместо `terminate`.  
  
 Существует один обработчик `set_unexpected` для всех динамически связанных DLL или EXE; даже при вызове `set_unexpected` обработчик может быть заменен другим или можно заменить обработчик с помощью других DLL или EXE.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`set_unexpected`|\<eh.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_unexpected](../Topic/_get_unexpected.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../Topic/unexpected%20\(CRT\).md)