---
title: _CrtSetReportMode
ms.date: 11/04/2016
api_name:
- _CrtSetReportMode
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CrtSetReportMode
- CrtSetReportMode
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
ms.openlocfilehash: ae7e83ac009d572f8a9f6484519b0cdfb7499ce3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938466"
---
# <a name="_crtsetreportmode"></a>_CrtSetReportMode

Задает назначение или назначения для конкретного типа отчета, созданного **_CrtDbgReport** , и все макросы, вызывающие [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md), такие как [_ASSERT, _ASSERTE, _ASSERT_EXPR Macros](assert-asserte-assert-expr-macros.md), [_ASSERT, _ASSERTE, _ ](assert-asserte-assert-expr-macros.md)Макросы ASSERT_EXPR, [_RPT, _RPTF, _RPTW, _RPTFW Macros](rpt-rptf-rptw-rptfw-macros.md), [_RPT, _RPTF, _RPTW, _RPTFW Macros](rpt-rptf-rptw-rptfw-macros.md) (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>Параметры

*reportType*<br/>
Тип отчета: **_CRT_WARN**, **_CRT_ERROR**и **_CRT_ASSERT**.

*репортмоде*<br/>
Новый режим или режимы работы с отчетами для *reportType*.

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении **_CrtSetReportMode** возвращает предыдущий режим или режимы отчета для типа отчета, указанного в *reportType*. Если в качестве *reportType* передается недопустимое значение или для *репортмоде*указан недопустимый режим, **_CrtSetReportMode** вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция **устанавливает** **еинвал** и возвращает-1. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_CrtSetReportMode** указывает назначение выходных данных для **_CrtDbgReport**. Поскольку макросы [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md), [_RPT](rpt-rptf-rptw-rptfw-macros.md)и [_RPTF](rpt-rptf-rptw-rptfw-macros.md) вызывают **_CrtDbgReport**, **_CrtSetReportMode** указывает место назначения вывода текста, указанного с помощью этих макросов.

Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtSetReportMode** удаляются во время предварительной обработки.

Если не вызвать **_CrtSetReportMode** для определения назначения вывода сообщений, действуют следующие значения по умолчанию:

- Ошибки и сбои проверочного утверждения направляются в окно сообщений отладчика.

- Предупреждения из Windows-приложений направляются в окно вывода отладчика.

- Предупреждения из консольных приложений не отображаются.

В следующей таблице перечислены типы сообщений, определенные в файле Crtdbg.h.

|Тип отчета|Описание|
|-----------------|-----------------|
|**_CRT_WARN**|Предупреждения, сообщения и сведения, не требующие немедленного внимания.|
|**_CRT_ERROR**|Ошибки, неустранимые проблемы и ситуации, которые требуют немедленного внимания.|
|**_CRT_ASSERT**|Ошибки утверждений (утвержденные выражения, принимающие **значение false**).|

Функция **_CrtSetReportMode** назначает новый режим отчета, указанный в *репортмоде* , типу отчета, указанному в *reportType* , и возвращает ранее определенный режим отчета для *reportType*. В следующей таблице перечислены доступные варианты для *репортмоде* и результирующее поведение **_CrtDbgReport**. Эти параметры задаются в виде битовых флагов в файле Crtdbg.h.

|Режим отчета|Поведение функции _CrtDbgReport|
|-----------------|-----------------------------|
|**_CRTDBG_MODE_DEBUG**|Выводит сообщение в окно вывода отладчика.|
|**_CRTDBG_MODE_FILE**|Выводит сообщение в предоставленный пользователем дескриптор файла. Для определения конкретного файла или потока, используемого в качестве места назначения, необходимо вызвать функцию [_CrtSetReportFile](crtsetreportfile.md).|
|**_CRTDBG_MODE_WNDW**|Создает окно сообщения для вывода сообщения вместе с кнопками [прервать](abort.md), **повторить**и **пропустить** .|
|**_CRTDBG_REPORT_MODE**|Возвращает *репортмоде* для указанного *reportType*:<br /><br /> 1   **_CRTDBG_MODE_FILE**<br /><br /> 2 **_CRTDBG_MODE_DEBUG**<br /><br /> 4 **_CRTDBG_MODE_WNDW**|

Каждый тип отчета может создаваться с использованием одного, двух или трех режимов или вообще без режима. Следовательно, для одного типа отчета может быть задано несколько мест назначения. Например, следующий фрагмент кода вызывает отправку проверочных ошибок как в окно сообщения отладки, так и в **stderr**:

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

Кроме того, режимом или режимами отчетов можно управлять отдельно для каждого типа отчета. Например, можно указать, что *reportType* **_CRT_WARN** будет отправляться в выходную отладочную строку, тогда как **_CRT_ASSERT** будет отображаться с помощью окна сообщения об отладке и отправлены в **stderr**, как было показано ранее.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_CrtSetReportMode**|\<crtdbg.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Libraries** Только отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
