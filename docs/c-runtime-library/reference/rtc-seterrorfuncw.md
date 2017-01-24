---
title: "_RTC_SetErrorFuncW | Microsoft Docs"
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
  - "_RTC_SetErrorFuncW"
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
  - "_RTC_SetErrorFuncW"
  - "RTC_SetErrorFuncW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ошибки во время выполнения"
  - "RTC_SetErrorFuncW - функция"
  - "_RTC_error_fnW typedef"
  - "_RTC_SetErrorFuncW - функция"
  - "RTC_error_fnW typedef"
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_SetErrorFuncW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Назначает функцию в качестве обработчика для сообщений о проверке на ошибки во время выполнения \(RTC\).  
  
## Синтаксис  
  
```  
  
_RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW  
 function   
);  
  
```  
  
#### Параметры  
 `function`  
 Адрес функции, которая будет обрабатывать проверки на ошибки во время выполнения.  
  
## Возвращаемое значение  
 Ранее определенная функция обработки ошибок или `NULL`, если нет ранее определенной функции.  
  
## Заметки  
 В новом коде используйте только `_RTC_SetErrorFuncW`.`_RTC_SetErrorFunc` включена в библиотеку только для обеспечения обратной совместимости.  
  
 Обратный вызов `_RTC_SetErrorFuncW` применяется только к компоненту, с которым он был связан, но не глобально.  
  
 Убедитесь, что передаваемый в `_RTC_SetErrorFuncW` адрес относится к допустимой функции обработки ошибок.  
  
 Если ошибке назначен тип "–1" путем использования [\_RTC\_SetErrorType](../Topic/_RTC_SetErrorType.md), функция обработки ошибок не вызывается.  
  
 Перед тем, как вы сможете вызвать эту функцию, необходимо сначала вызвать одну из функций инициализации проверки на ошибки во время выполнения. Для получения дополнительной информации см. [Использование проверки кода во время выполнения без библиотеки среды выполнения C](../Topic/Using%20Run-Time%20Checks%20Without%20the%20C%20Run-Time%20Library.md).  
  
 **\_RTC\_error\_fnW** определяется следующим образом:  
  
 **typedef int \(\_\_cdecl \*\_RTC\_error\_fnW\)\(int**  `errorType` **, const wchar\_t \*** *filename* **, int**  *linenumber* **, const wchar\_t \*** `moduleName` **, const wchar\_t \*** *format* **, ...\);**  
  
 Здесь:  
  
 `errorType`  
 Тип ошибки, указанной [\_RTC\_SetErrorType](../Topic/_RTC_SetErrorType.md).  
  
 *filename*  
 Исходный файл, где произошел сбой, или значение NULL, если информация об отладке недоступна.  
  
 *linenumber*  
 Строка *filename*, где произошел сбой, или 0, если информация об отладке недоступна.  
  
 `moduleName`  
 Библиотека DLL или имя исполняемого файла, где произошел сбой.  
  
 *format*  
 Строка в стиле printf для отображения сообщения об ошибке с использованием оставшихся параметров. Первый аргумент VA\_ARGLIST — номер возникшей ошибки RTC.  
  
 Пример, в котором показано, как использовать **\_RTC\_error\_fnW**, см. в статье [Настройка проверок во время выполнения машинного кода](../Topic/Native%20Run-Time%20Checks%20Customization.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h\>|  
  
 Для получения дополнительной информации см. [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Проверка ошибок во время выполнения](../Topic/Run-Time%20Error%20Checking.md)