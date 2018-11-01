---
title: _CrtSetReportHook
ms.date: 11/04/2016
apiname:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
ms.openlocfilehash: 7dcb916ea920751618ffa6a4afbcde8df5e35cba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478342"
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook

Устанавливает определяемую клиентом функцию отчетов путем ее прикрепления к процессу создания отчетов среды выполнения языка C (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
_CRT_REPORT_HOOK _CrtSetReportHook(
   _CRT_REPORT_HOOK reportHook
);
```

### <a name="parameters"></a>Параметры

*reportHook*<br/>
Новая определяемая клиентом функция отчетов, которую необходимо прикрепить к процессу создания отчетов среды выполнения языка C.

## <a name="return-value"></a>Возвращаемое значение

Возвращает предыдущую определяемую клиентом функцию отчетов.

## <a name="remarks"></a>Примечания

**_CrtSetReportHook** позволяет приложению использовать собственную reporting функция библиотеки среды выполнения языка C, процедуры составления отчетности. В результате всякий раз, когда для создания отчета отладки вызывается функция [_CrtDbgReport](crtdbgreport-crtdbgreportw.md), сначала вызывается функция отчетов приложения. Эта функция позволяет приложению выполнять операции, такие как фильтрация отчетов отладки, поэтому он может сосредоточиться на конкретных типов выделения, или отправить отчет в назначения, не доступные с помощью **_CrtDbgReport**. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtSetReportHook** удаляются во время предварительной обработки.

Для более надежную версию функции **_CrtSetReportHook**, см. в разделе [_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md).

**_CrtSetReportHook** функция устанавливает новую определяемую клиентом функцию, указанную в отчетов *reportHook* и возвращает предыдущий ловушка определяемую клиентом. В следующем примере показано, как должен быть объявлен прототип определяемого клиентом обработчика отчетов:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

где *reportType* является тип отчета отладки (**_CRT_WARN**, **_CRT_ERROR**, или **_CRT_ASSERT**), *сообщения* является полностью собранное пользовательское отладочное сообщение должен содержаться в отчете, и **returnValue** является значение, заданное параметром определяемую клиентом функцией отчетов, которое должен вернуть **_ CrtDbgReport**. Полное описание доступных типов отчетов см. в описании функции [_CrtSetReportMode](crtsetreportmode.md).

Если определяемая клиентом функция отчетов полностью обрабатывает сообщение отладки такие дальнейшая выдача отчета не требуется, она должна возвращать. **TRUE**. Если функция возвращает **FALSE**, **_CrtDbgReport** вызывается для формирования отчета об отладке с использованием текущих параметров для типа отчета, режима и файла. Кроме того, указав **_CrtDbgReport** возвращаемое значение в **returnValue**, приложение можно также контролировать, происходит ли прерывание отладки. Полное описание того, как отчет об отладке настроен и создан, см. в разделе **_CrtSetReportMode**, [_CrtSetReportFile](crtsetreportfile.md), и **_CrtDbgReport**.

Дополнительные сведения о других допускающих подключение функциях среды выполнения и написании собственных определяемых клиентом функциях-ловушках см. в разделе [Написание функций отладочных ловушек](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> Если приложение компилируется с **/CLR** и функция отчетов вызывается после выхода из приложения основной, CLR вызовет исключение, если функция отчетов вызывает функции CRT.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtSetReportHook**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
