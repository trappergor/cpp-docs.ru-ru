---
title: "raise | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "raise"
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
  - "Raise"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "программы [C++], отправка сигналов в исполняющие программы"
  - "raise - функция"
  - "сигналы"
  - "сигналы, отправка в исполняющие программы"
ms.assetid: a3ccd3ad-f68f-4a7b-a005-c3ebfb217e8b
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# raise
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Отправляет сигнал выполняющейся программе.  
  
> [!NOTE]
>  Не используйте этот метод для завершения приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], за исключением сценариев тестирования или отладки.  Закрытие приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] программным способом или с помощью пользовательского интерфейса на допускается в соответствии с разделом 3.6 [сертификационных требований к приложениям для Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889).  Дополнительные сведения см. в разделе [Жизненный цикл приложения \(приложения Магазина Windows\)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Синтаксис  
  
```  
  
      int raise(  
int sig   
);  
```  
  
#### Параметры  
 *sig*  
 Сигнал, который нужно послать.  
  
## Возвращаемое значение  
 Если операция завершилась удачно, **raise** возвращает 0.  В противном случае возвращается ненулевое значение.  
  
## Заметки  
 Функция **raise** отправляет *sig* выполняющейся программе.  Если предыдущий вызов функции **signal** установил функцию, обрабатывающую сигналы, для *sig*, **raise** выполняет эту функцию.  Если функция обработки не задана, то выполняется действие по умолчанию, связанное со значением сигнала *sig*, как показано ниже.  
  
|Сигнал|Значение|По умолчанию|  
|------------|--------------|------------------|  
|`SIGABRT`|Аварийное завершение|Завершает вызывающую программу с кодом завершения 3|  
|`SIGFPE`|Ошибка в операции с плавающей запятой|Завершает вызывающую программу|  
|`SIGILL`|Недопустимая инструкция|Завершает вызывающую программу|  
|`SIGINT`|Прерывание CTRL\+C|Завершает вызывающую программу|  
|`SIGSEGV`|Недопустимый доступ к хранилищу|Завершает вызывающую программу|  
|`SIGTERM`|Программе отправлен запрос на завершение|Игнорирует сигнал|  
  
 Если аргумент не является допустимым сигналом, как описано выше, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если сигнал не обработан, функция устанавливает `errno` в `EINVAL` и возвращает ненулевое значение.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|**raise**|\<signal.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [signal](../../c-runtime-library/reference/signal.md)