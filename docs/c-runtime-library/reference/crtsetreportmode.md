---
title: "_CrtSetReportMode | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: b7e3cb7562fb63467ef0e0ee28861936fb820fa3
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="crtsetreportmode"></a>_CrtSetReportMode
Определяет место или места назначения для определенного типа отчетов, создаваемых функцией `_CrtDbgReport`, а также для любых макросов, которые вызывают функции [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md), таких как макросы [_ASSERT, _ASSERTE, _ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_ASSERT, _ASSERTE, _ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_RPT, _RPTF, _RPTW, _RPTFW](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) и [_RPT, _RPTF, _RPTW, _RPTFW](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) (только в отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `reportType`  
 Тип отчета: `_CRT_WARN`, `_CRT_ERROR` и `_CRT_ASSERT`.  
  
 `reportMode`  
 Новый режим или режимы отчетов для `reportType`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном завершении функция `_CrtSetReportMode` возвращает предыдущий режим или режимы отчетов для типа отчета, указанного в параметре `reportType`. Если в параметре `reportType` передано недопустимое значение или для параметра `reportMode` указан недопустимый режим, функция `_CrtSetReportMode` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функции задает для `errno` значение `EINVAL` и возвращает -1. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtSetReportMode` определяет место назначения вывода для функции `_CrtDbgReport`. Поскольку макросы `_ASSERT`, `_ASSERTE`, `_RPT` и `_RPTF` вызывают функцию `_CrtDbgReport`, функция `_CrtSetReportMode` определяет место назначения вывода текста, определенного этими макросами.  
  
 Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtSetReportMode` удаляются на этапе предварительной обработки.  
  
 Если функция `_CrtSetReportMode` не вызывается для определения места назначения вывода сообщений, используются следующие действия по умолчанию:  
  
-   Ошибки и сбои проверочного утверждения направляются в окно сообщений отладчика.  
  
-   Предупреждения из Windows-приложений направляются в окно вывода отладчика.  
  
-   Предупреждения из консольных приложений не отображаются.  
  
 В следующей таблице перечислены типы сообщений, определенные в файле Crtdbg.h.  
  
|Тип отчета|Описание|  
|-----------------|-----------------|  
|`_CRT_WARN`|Предупреждения, сообщения и сведения, не требующие немедленного внимания.|  
|`_CRT_ERROR`|Ошибки, неустранимые проблемы и ситуации, которые требуют немедленного внимания.|  
|`_CRT_ASSERT`|Сбои проверочного утверждения (выражения, вычисление которых дает значение `FALSE`).|  
  
 Функция `_CrtSetReportMode` присваивает новый режим отчета, указанный в параметре `reportMode`, типу отчета, указанному в параметре `reportType`, и возвращает ранее определенный режим отчета для `reportType`. В следующей таблице приведен список доступных вариантов для параметра `reportMode` и соответствующее поведение функции `_CrtDbgReport`. Эти параметры задаются в виде битовых флагов в файле Crtdbg.h.  
  
|Режим отчета|Поведение функции _CrtDbgReport|  
|-----------------|-----------------------------|  
|`_CRTDBG_MODE_DEBUG`|Выводит сообщение в окно вывода отладчика.|  
|`_CRTDBG_MODE_FILE`|Выводит сообщение в предоставленный пользователем дескриптор файла. Для определения конкретного файла или потока, используемого в качестве места назначения, необходимо вызвать функцию [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md).|  
|`_CRTDBG_MODE_WNDW`|Создает окно сообщения для отображения сообщения вместе с кнопками `Abort`, `Retry` и `Ignore`.|  
|`_CRTDBG_REPORT_MODE`|Возвращает `reportMode` для заданного `reportType`:<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 Каждый тип отчета может создаваться с использованием одного, двух или трех режимов или вообще без режима. Следовательно, для одного типа отчета может быть задано несколько мест назначения. Например, в следующем фрагменте кода сообщения о сбоях проверочного утверждения отправляются как в окно сообщений отладчика, так и в поток `stderr`:  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 Кроме того, режимом или режимами отчетов можно управлять отдельно для каждого типа отчета. Например, можно указать, что `reportType` `_CRT_WARN` отправляется в выходную отладочную строку, а `_CRT_ASSERT` отображается с помощью окна сообщений отладчика и отправляется в поток `stderr`, как показано ранее.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportMode`|\<crtdbg.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** только отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)
