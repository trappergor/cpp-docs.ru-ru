---
title: _CrtSetReportMode
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
ms.openlocfilehash: 2096d39a8ba316fc76c97517a16e34231940e7f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335299"
---
# <a name="crtsetreportmode"></a>_CrtSetReportMode

Указывает назначения (назначений) для определенного типа отчета созданные **_CrtDbgReport** и всеми макросами, которые вызывают [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md), такие как [_ASSERT, _ASSERTE, Макрос _ASSERT_EXPR](assert-asserte-assert-expr-macros.md), [_ASSERT, _ASSERTE, _ASSERT_EXPR макросы](assert-asserte-assert-expr-macros.md), [макросы _RPT, _RPTF, _RPTW, _RPTFW Macros](rpt-rptf-rptw-rptfw-macros.md), и [макросы _RPT, _RPTF, _RPTW, _RPTFW Macros](rpt-rptf-rptw-rptfw-macros.md) (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>Параметры

*reportType*<br/>
Тип отчета: **_CRT_WARN**, **_CRT_ERROR**, и **_CRT_ASSERT**.

*reportMode*<br/>
Новый режим или режимы отчетов для *reportType*.

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении **_CrtSetReportMode** возвращает предыдущий режим или режимы отчетов для типа отчета, указанного в *reportType*. Если недопустимое значение передается в качестве *reportType* для указан недопустимый режим или *reportMode*, **_CrtSetReportMode** вызывает обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает – 1. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_CrtSetReportMode** Указывает выходное назначение для **_CrtDbgReport**. Поскольку макросы [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md), [_RPT](rpt-rptf-rptw-rptfw-macros.md), и [_RPTF](rpt-rptf-rptw-rptfw-macros.md) вызвать **_CrtDbgReport**, **_CrtSetReportMode** указывает место назначения вывода текста, определенного этими макросами.

Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtSetReportMode** удаляются во время предварительной обработки.

Если вы не вызываете **_CrtSetReportMode** для определения места назначения вывода сообщений, выберите следующие значения по умолчанию вступают в силу:

- Ошибки и сбои проверочного утверждения направляются в окно сообщений отладчика.

- Предупреждения из Windows-приложений направляются в окно вывода отладчика.

- Предупреждения из консольных приложений не отображаются.

В следующей таблице перечислены типы сообщений, определенные в файле Crtdbg.h.

|Тип отчета|Описание|
|-----------------|-----------------|
|**_CRT_WARN**|Предупреждения, сообщения и сведения, не требующие немедленного внимания.|
|**_CRT_ERROR**|Ошибки, неустранимые проблемы и ситуации, которые требуют немедленного внимания.|
|**_CRT_ASSERT**|Сбои проверочных утверждений (сигнал выражения, результатом вычисления которых **FALSE**).|

**_CrtSetReportMode** функция присваивает новый режим отчета, указанный в *reportMode* , типу отчета, указанного в *reportType* и возвращает ранее определенный режим отчета для *reportType*. В следующей таблице перечислены доступные варианты для *reportMode* и соответствующее поведение функции **_CrtDbgReport**. Эти параметры задаются в виде битовых флагов в файле Crtdbg.h.

|Режим отчета|Поведение функции _CrtDbgReport|
|-----------------|-----------------------------|
|**_CRTDBG_MODE_DEBUG**|Выводит сообщение в окно вывода отладчика.|
|**_CRTDBG_MODE_FILE**|Выводит сообщение в предоставленный пользователем дескриптор файла. Для определения конкретного файла или потока, используемого в качестве места назначения, необходимо вызвать функцию [_CrtSetReportFile](crtsetreportfile.md).|
|**_CRTDBG_MODE_WNDW**|Создает окно сообщения для отображения сообщения вместе с [прервать](abort.md), **повторите**, и **пропустить** кнопки.|
|**_CRTDBG_REPORT_MODE**|Возвращает *reportMode* для указанного *reportType*:<br /><br /> 1   **_CRTDBG_MODE_FILE**<br /><br /> 2   **_CRTDBG_MODE_DEBUG**<br /><br /> 4   **_CRTDBG_MODE_WNDW**|

Каждый тип отчета может создаваться с использованием одного, двух или трех режимов или вообще без режима. Следовательно, для одного типа отчета может быть задано несколько мест назначения. Например, в следующем фрагменте кода вызывает сбои проверочных утверждений, отправляемых в обоих окно сообщений отладки и **stderr**:

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

Кроме того, режимом или режимами отчетов можно управлять отдельно для каждого типа отчета. Например, можно указать, что *reportType* из **_CRT_WARN** быть отправлено выходную отладочную строку, тогда как **_CRT_ASSERT** быть отображается с помощью окно сообщений отладки и отправляются в **stderr**, как показано ранее.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_CrtSetReportMode**|\<crtdbg.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** Отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md) только.

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
