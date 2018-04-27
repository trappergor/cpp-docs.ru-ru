---
title: Макросы _RPT, _RPTF, _RPTW, _RPTFW Macros | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 1692789ff2dac85e6ca33aa6b05ced6a01f30cba
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>Макросы _RPT, _RPTF, _RPTW, _RPTFW

Отслеживает ход выполнения приложения путем создания отчета отладки (только отладочная версия). Обратите внимание, что *n* указывает число аргументов в *args* и может быть 0, 1, 2, 3, 4 или 5.

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

*reportType функции* тип отчета: **_CRT_WARN**, **_CRT_ERROR**, или **_CRT_ASSERT**.

*формат* строка управления форматом, используемый для создания пользовательского сообщения.

*args* аргументы подстановки, используемые *формат*.

## <a name="remarks"></a>Примечания

Эти макросы занять *reportType функции* и *формат* параметров. Кроме того, они также могут принимать до четырех дополнительных аргументов, обозначенных числом, добавленным к имени макроса. Например **_RPT0** и **_RPTF0** не принимают дополнительные аргументы, **_RPT1** и **_RPTF1** принимать *arg1*, **_RPT2** и **_RPTF2** принимать *arg1* и **arg2**, и т. д.

**_RPT** и **_RPTF** макросы похожи на [printf](printf-printf-l-wprintf-wprintf-l.md) работать, так как они могут использоваться для отслеживания хода выполнения приложения в процессе отладки. Тем не менее, эти макросы обеспечивают большую гибкость, чем **printf** , так как они не обязательно должны быть заключены в **#ifdef** инструкции, чтобы предотвратить их вызывается в окончательной сборке приложения. Такая гибкость достигается с помощью [_DEBUG](../../c-runtime-library/debug.md) макрос; **_RPT** и **_RPTF** макросы доступны только тогда, когда **_DEBUG** установлен флаг определен. Когда **_DEBUG** — не определен, вызовы этих макросов удаляются во время предварительной обработки.

**_RPTW** и **_RPTFW** макросы, версии этих макросов для расширенных символов. Они подобны **wprintf** и принимают в качестве аргументов строки расширенных символов.

**_RPT** вызовов макросов [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) функцию для создания отчета об отладке с пользовательским сообщением. **_RPTW** вызовов макросов **_CrtDbgReportW** функция создает один и тот же отчет с расширенными символами. **_RPTF** и **_RPTFW** макросы создания отчета об отладке с исходного файла и номер строки которой был вызван макрос отчета, в дополнение к сообщение для пользователя. Сообщение для пользователя, созданного путем замены **arg**[*n*] аргументы в *формат* строку, с использованием того же правилами, определенными в [printf](printf-printf-l-wprintf-wprintf-l.md)функции.

**_CrtDbgReport** или **_CrtDbgReportW** создает отчет об отладке и определяет его назначения на основании текущих режимов отчета и файла, определенного для *reportType функции*. Функции [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md) используются для определения мест назначения для каждого типа отчета.

Если **_RPT** вызван макрос и ни **_CrtSetReportMode** , ни **_CrtSetReportFile** был вызван, сообщения отображаются следующим образом.

|Тип отчета|Назначение выходных данных|
|-----------------|------------------------|
|**_CRT_WARN**|Текст предупреждения не отображается.|
|**_CRT_ERROR**|Всплывающее окно. То же самое, как если бы была указана функция `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);`.|
|**_CRT_ASSERT**|То же, что **_CRT_ERROR**.|

Если назначением является окно сообщений отладки и пользователь нажимает кнопку **повторите** кнопки, **_CrtDbgReport** или **_CrtDbgReportW** возвращает 1, в результате чего макросы для запуска отладчик, условии, что just-in-time (JIT) отладки. Дополнительные сведения об использование этих макросов в качестве механизма обработки ошибок при отладке см. в разделе [Использование макросов для проверки и создания отчетов](/visualstudio/debugger/macros-for-reporting).

Существуют два других макроса, которые создают отчеты отладки. Макрос [_ASSERT](assert-asserte-assert-expr-macros.md) создает отчет, но только если его аргумент-выражение принимает значение FALSE. [_ASSERTE](assert-asserte-assert-expr-macros.md) — точно like **_ASSERT**, но включает выражение в создаваемом отчете.

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
