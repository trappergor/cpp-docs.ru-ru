---
title: Макросы _RPT, _RPTF, _RPTW, _RPTFW
ms.date: 11/04/2016
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
ms.openlocfilehash: 567fe0a68f5adad6f5d90ef3da9d673a75bb83a6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949084"
---
# <a name="_rpt-_rptf-_rptw-_rptfw-macros"></a>Макросы _RPT, _RPTF, _RPTW, _RPTFW

Отслеживает ход выполнения приложения путем создания отчета отладки (только отладочная версия). Обратите внимание, что *n* указывает число аргументов в *args* и может принимать значения 0, 1, 2, 3, 4 или 5.

## <a name="syntax"></a>Синтаксис

```C
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

### <a name="parameters"></a>Параметры

*reportType*<br/>
Тип отчета: **_CRT_WARN**, **_CRT_ERROR**или **_CRT_ASSERT**.

*format*<br/>
Строка управления форматом, которая используется для создания пользовательского сообщения.

*args*<br/>
Аргументы подстановки, используемые в *формате*.

## <a name="remarks"></a>Примечания

Все эти макросы принимают параметры *reportType* и *Format* . Кроме того, они также могут принимать до четырех дополнительных аргументов, обозначенных числом, добавленным к имени макроса. Например, **_RPT0** и **_RPTF0** не принимают дополнительных аргументов, **_RPT1** и **_RPTF1** принимают *arg1*, **_RPT2** и **_RPTF2** принимают *arg1* и **arg2**и т. д.

Макросы **_RPT** и **_RPTF** похожи на функцию [printf](printf-printf-l-wprintf-wprintf-l.md) , так как их можно использовать для отслеживания хода выполнения приложения во время процесса отладки. Однако эти макросы являются более гибкими, чем **printf** , так как их не нужно заключать в **#ifdef** инструкции, чтобы предотвратить их вызов в розничной сборке приложения. Эта гибкость достигается с помощью макроса [_DEBUG](../../c-runtime-library/debug.md) ; макросы **_RPT** и **_RPTF** доступны только при определении флага **_DEBUG** . Если **_DEBUG** не определен, вызовы этих макросов удаляются во время предварительной обработки.

Макросы **_RPTW** и **_RPTFW** — это версии этих макросов для расширенных символов. Они подобны **wprintf** и принимают строки расширенных символов в качестве аргументов.

Макросы **_RPT** вызывают функцию [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) для создания отчета об отладке с сообщением пользователя. Макросы **_RPTW** вызывают функцию **_CrtDbgReportW** для создания того же отчета с расширенными символами. Макросы **_RPTF** и **_RPTFW** создают отчет об отладке с исходным файлом и номером строки, где был вызван макрос отчета, в дополнение к сообщению пользователя. Пользовательское сообщение создается путем подстановки аргументов **аргумента [** *n*] в строку *формата* с использованием тех же правил, которые определены функцией [printf](printf-printf-l-wprintf-wprintf-l.md) .

**_CrtDbgReport** или **_CrtDbgReportW** создает отчет об отладке и определяет его назначения на основе текущих режимов отчета и файла, определенного для *reportType*. Функции [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md) используются для определения мест назначения для каждого типа отчета.

Если вызывается макрос **_RPT** и не вызывался ни **_CrtSetReportMode** , ни **_CrtSetReportFile** , сообщения отображаются следующим образом.

|Тип отчета|Назначение выходных данных|
|-----------------|------------------------|
|**_CRT_WARN**|Текст предупреждения не отображается.|
|**_CRT_ERROR**|Всплывающее окно. То же самое, как если бы была указана функция `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);`.|
|**_CRT_ASSERT**|То же, что и **_CRT_ERROR**.|

Если назначением является окно сообщения об отладке, и пользователь нажимает кнопку **повторить** , **_CrtDbgReport** или **_CrtDbgReportW** возвращает 1, что приводит к запуску отладчика с помощью этих макросов при условии, что JIT-отладка включена. Дополнительные сведения об использование этих макросов в качестве механизма обработки ошибок при отладке см. в разделе [Использование макросов для проверки и создания отчетов](/visualstudio/debugger/macros-for-reporting).

Существуют два других макроса, которые создают отчеты отладки. Макрос [_ASSERT](assert-asserte-assert-expr-macros.md) создает отчет, но только если его аргумент-выражение принимает значение FALSE. [_ASSERTE](assert-asserte-assert-expr-macros.md) точно аналогичен **_ASSERT**, но содержит выражение Failed в созданном отчете.

## <a name="requirements"></a>Требования

|Макрос|Обязательный заголовок|
|-----------|---------------------|
|**_RPT** макросы|\<crtdbg.h>|
|**_RPTF** макросы|\<crtdbg.h>|
|**_RPTW** макросы|\<crtdbg.h>|
|**_RPTFW** макросы|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

Хотя эти макросы получаются путем включения файла Crtdbg.h, приложение должно подключить одну из отладочных библиотек, поскольку макросы вызывают другие функции времени выполнения.

## <a name="example"></a>Пример

См. пример в разделе [_ASSERT](assert-asserte-assert-expr-macros.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
