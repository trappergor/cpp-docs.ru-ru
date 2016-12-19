---
title: "_CrtSetReportMode | Microsoft Docs"
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
  - "_CrtSetReportMode"
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
  - "_CrtSetReportMode"
  - "CrtSetReportMode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtSetReportMode - функция"
  - "CrtSetReportMode - функция"
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetReportMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает назначение или назначения для определенного типа отчета, создаваемого `_CrtDbgReport` и всеми макросами, которые вызывают [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md), например [Макросы \_ASSERT, \_ASSERTE, \_ASSERT\_EXPR](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md), [Макросы \_ASSERT, \_ASSERTE, \_ASSERT\_EXPR](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md), [Макросы \_RPT, \_RPTF, \_RPTW, \_RPTFW](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md) и [Макросы \_RPT, \_RPTF, \_RPTW, \_RPTFW](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md) \(только отладочная версия\).  
  
## Синтаксис  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### Параметры  
 `reportType`  
 Тип отчета: `_CRT_WARN`, `_CRT_ERROR` и `_CRT_ASSERT`.  
  
 `reportMode`  
 Новый режим или режимы отчетов для `reportType`.  
  
## Возвращаемое значение  
 При успешном завершении `_CrtSetReportMode` возвращает предыдущий режим или режимы отчетов для определенного типа отчета в `reportType`.  Если недопустимое значение передается как `reportType` или недопустимый режим определен для `reportMode`, `_CrtSetReportMode` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция устанавливает `errno` в значение `EINVAL` и возвращает \-1.  Дополнительные сведения см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 `_CrtSetReportMode` определяет выходное назначение для `_CrtDbgReport`.  Поскольку макросы `_ASSERT`, `_ASSERTE`, `_RPT` и `_RPTF` вызывают `_CrtDbgReport`, `_CrtSetReportMode` определяет выходное назначение текста, определенного этими макросами.  
  
 Если [\_DEBUG](../Topic/_DEBUG.md) не определен, то вызовы `_CrtSetReportMode` удаляются во время предварительной обработки.  
  
 Если не вызывается `_CrtSetReportMode` для определения назначения вывода сообщений, используются следующие действия по умолчанию:  
  
-   Ошибки и сбои проверочного утверждения направляются в окно сообщений отладчика.  
  
-   Предупреждения из Windows\-приложений отправляются в окно вывода отладчика.  
  
-   Предупреждения из консольных приложений не отображаются.  
  
 В следующей таблице перечислены типы сообщений, определенные в Crtdbg.h.  
  
|Тип отчета|Описание|  
|----------------|--------------|  
|`_CRT_WARN`|Предупреждения, сообщения и сведения, не требующие немедленного внимания.|  
|`_CRT_ERROR`|Ошибки, неустранимые проблемы и ситуации, которые требуют немедленного внимания.|  
|`_CRT_ASSERT`|Сбои проверочного утверждения \(выражения проверки, результат вычисления которых `FALSE`\).|  
  
 Функция `_CrtSetReportMode` присваивает новый режим отчета, указанный в `reportMode` типу отчета, указанному в `reportType`, и возвращает ранее определенный режим отчета для `reportType`.  В следующей таблице приведен список доступных вариантов для `reportMode` и результирующее поведение `_CrtDbgReport`.  Эти параметры задаются в виде битовых флагов в Crtdbg.h.  
  
|Режим отчета|Поведение \_CrtDbgReport|  
|------------------|------------------------------|  
|`_CRTDBG_MODE_DEBUG`|Пишет сообщение в окно вывода отладчика.|  
|`_CRTDBG_MODE_FILE`|Пишет сообщение в предоставленный пользователем обработчик файлов.  [\_CrtSetReportFile](../Topic/_CrtSetReportFile.md) должен быть вызван, чтобы определить конкретные файл или поток для использования в качестве места назначения.|  
|`_CRTDBG_MODE_WNDW`|Создает окно сообщения для отображения сообщения вместе с кнопками `Abort`, `Retry` и `Ignore`.|  
|`_CRTDBG_REPORT_MODE`|Возвращает `reportMode` для заданного `reportType`:<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 Каждый тип отчета может быть использован с помощью одной, двух или трех моделей или без моделей вообще.  Следовательно, можно иметь несколько назначений, заданных для одного типа отчета.  Например, в следующем фрагменте кода сообщения о сбоях проверочного утверждения отправляются и в окно сообщений отладчика, и в `stderr`:  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 Кроме того, режимом или режимами отчетов можно управлять отдельно для каждого типа отчета.  Например, можно указать, что `reportType` `_CRT_WARN` отправляется в вывод отладочной строки, а `_CRT_ASSERT` отображается с помощью окна сообщений отладчика и отправляется в `stderr`, как показано ранее.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_CrtSetReportMode`|\<crtdbg.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 Версии **Библиотеки:** Отладочные версии только для [Особенности библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)