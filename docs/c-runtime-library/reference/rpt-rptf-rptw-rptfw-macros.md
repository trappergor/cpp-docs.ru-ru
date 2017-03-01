---
title: "Макросы _RPT, _RPTF, _RPTW, _RPTFW Macros | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- RPT3
- RPTF4
- _RPT4
- RPT1
- _RPTF0
- RPTF3
- _RPTF4
- RPTF1
- RPT4
- _RPT1
- _RPT0
- RPT0
- _RPTF2
- RPTF0
- _RPT3
- _RPT2
- _RPTF3
- RPT2
- _RPTF1
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _RPTW3 macro
- _RPT0 macro
- RPTW4 macro
- _RPTF3 macro
- _RPTW4 macro
- RPTF4 macro
- RPTFW2 macro
- RPTW macros
- RPT1 macro
- _RPTF macros
- RPTFW3 macro
- _RPTW0 macro
- _RPTF0 macro
- macros, debugging with
- _RPTW2 macro
- RPTF3 macro
- RPT3 macro
- RPT0 macro
- _RPT macros
- RPTW3 macro
- _RPTFW macros
- debug reporting macros
- RPTF macros
- RPT macros
- _RPTW macros
- RPTF2 macro
- _RPTF1 macro
- _RPT1 macro
- _RPT4 macro
- _RPTFW2 macro
- _RPTFW1 macro
- RPTF0 macro
- _RPT2 macro
- RPTFW macros
- _RPTW1 macro
- _RPTFW0 macro
- RPT4 macro
- _RPT3 macro
- _RPTFW3 macro
- _RPTF4 macro
- _RPTFW4 macro
- _RPTF2 macro
- RPTW0 macro
- RPTFW4 macro
- RPTFW0 macro
- RPTW2 macro
- RPTF1 macro
- RPT2 macro
- RPTFW1 macro
- RPTW1 macro
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d8611402652268e0a85170a36355619e5c7335ac
ms.lasthandoff: 02/24/2017

---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>Макросы _RPT, _RPTF, _RPTW, _RPTFW
Отслеживает ход выполнения приложения путем создания отчета отладки (только отладочная версия). Обратите внимание, что *n* определяет количество аргументов в параметре `args` и может быть 0, 1, 2, 3, 4 или 5.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      _RPT  
      n  
      (  
   reportType,  
   format,  
...[args]  
);  
_RPTFn(  
   reportType,  
   format,  
   [args]  
);  
_RPTWn(  
   reportType,  
   format   
   [args]  
);  
_RPTFWn(  
   reportType,  
   format   
   [args]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `reportType`  
 Тип отчета: `_CRT_WARN`, `_CRT_ERROR` или `_CRT_ASSERT`.  
  
 `format`  
 Строка управления форматом, которая используется для создания пользовательского сообщения.  
  
 `args`  
 Аргументы подстановки, используемые параметром `format`.  
  
## <a name="remarks"></a>Примечания  
 Все эти макросы принимают параметры `reportType` и `format`. Кроме того, они также могут принимать до четырех дополнительных аргументов, обозначенных числом, добавленным к имени макроса. Например, макросы `_RPT0` и `_RPTF0` не принимают дополнительные аргументы, макросы `_RPT1` и `_RPTF1` принимают `arg1`, макросы `_RPT2` и `_RPTF2` принимают `arg1` и `arg2` и т. д.  
  
 Макросы `_RPT` и `_RPTF` аналогичны функции [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), поскольку их можно использовать для отслеживания хода выполнения приложения в процессе отладки. Однако эти макросы обеспечивают большую гибкость, чем функция `printf`, поскольку нет необходимости включать их в операторы `#ifdef`, чтобы предотвратить их вызов в коммерческой сборке приложения. Эта гибкость достигается с помощью макроса [_DEBUG](../../c-runtime-library/debug.md); макросы `_RPT` и `_RPTF` доступны только в том случае, если определен флаг `_DEBUG`. Если флаг `_DEBUG` не определен, вызовы этих макросов удаляются во время предварительной обработки.  
  
 Макросы `_RPTW` и `_RPTFW` являются версиями этих макросов для расширенных символов. Они подобны функции `wprintf` и принимают в качестве аргументов строки расширенных символов.  
  
 Макросы `_RPT` вызывают функцию [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) для создания отчета по отладке с пользовательским сообщением. Макросы `_RPTW` вызывают функцию `_CrtDbgReportW` для создания того же отчета с расширенными символами. Макросы `_RPTF` и `_RPTFW` создают отчеты отладки, в котором помимо пользовательского сообщения указан файл исходного кода и номер строки, в которой был вызван макрос отчета. Пользовательское сообщение создается путем замены аргументов `arg`[*n*] в строке `format`, используя те же правила, которые определены функцией [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 Функция `_CrtDbgReport` или `_CrtDbgReportW` создает отчет отладки и определяет места его назначения на основании текущих режимов отчета и файла, определенных для `reportType`. Функции [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) и [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) используются для определения мест назначения для каждого типа отчета.  
  
 Если вызывается макрос `_RPT` и при этом не вызывается ни одна из функций `_CrtSetReportMode` и `_CrtSetReportFile`, сообщения отображаются следующим образом.  
  
|Тип отчета|Назначение выходных данных|  
|-----------------|------------------------|  
|`_CRT_WARN`|Текст предупреждения не отображается.|  
|`_CRT_ERROR`|Всплывающее окно. То же самое, как если бы была указана функция `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);`.|  
|`_CRT_ASSERT`|Эквивалентно `_CRT_ERROR`.|  
  
 Когда место назначения — это окно сообщения отладки и пользователь нажимает кнопку **Повторить**, функция `_CrtDbgReport` или `_CrtDbgReportW` возвращает значение 1, в результате чего макросы запускают отладчик, если включена JIT-отладка. Дополнительные сведения об использование этих макросов в качестве механизма обработки ошибок при отладке см. в разделе [Использование макросов для проверки и создания отчетов](/visualstudio/debugger/macros-for-reporting).  
  
 Существуют два других макроса, которые создают отчеты отладки. Макрос [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) создает отчет, но только если его аргумент-выражение принимает значение FALSE. Макрос [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) выполняется точно так же, как и макрос `_ASSERT`, но включает выражение в созданный отчет.  
  
## <a name="requirements"></a>Требования  
  
|Макрос|Обязательный заголовок|  
|-----------|---------------------|  
|Макрос `_RPT`|\<crtdbg.h>|  
|Макрос `_RPTF`|\<crtdbg.h>|  
|Макрос `_RPTW`|\<crtdbg.h>|  
|Макрос `_RPTFW`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
 Хотя эти макросы получаются путем включения файла Crtdbg.h, приложение должно подключить одну из отладочных библиотек, поскольку макросы вызывают другие функции времени выполнения.  
  
## <a name="example"></a>Пример  
 См. пример в разделе [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)
