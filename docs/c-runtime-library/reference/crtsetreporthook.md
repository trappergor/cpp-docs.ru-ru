---
title: _CrtSetReportHook | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ef76fe0b7befb99b5bf0e8bb69fa1a1229782de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398793"
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

**_CrtSetReportHook** позволяет приложению использовать собственную reporting функцию в библиотеку времени выполнения отладки C процессу отчетов. В результате всякий раз, когда для создания отчета отладки вызывается функция [_CrtDbgReport](crtdbgreport-crtdbgreportw.md), сначала вызывается функция отчетов приложения. Это позволяет приложению выполнять операции, такие как фильтрация отчетов отладки, его можно сосредоточиться на определенных типов выделения памяти или отправить отчет в назначения, не доступные с помощью **_CrtDbgReport**. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtSetReportHook** удаляются на этапе предварительной обработки.

Для более надежную версию функции **_CrtSetReportHook**, в разделе [_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md).

**_CrtSetReportHook** функция устанавливает новую определяемую клиентом отчетов функции, указанной в *reportHook* и возвращает предыдущего обработчика определяемую клиентом. В следующем примере показано, как должен быть объявлен прототип определяемого клиентом обработчика отчетов:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

где *reportType функции* является тип отчета отладки (**_CRT_WARN**, **_CRT_ERROR**, или **_CRT_ASSERT**), *сообщения* является полностью собранное пользовательское отладочное сообщение должен содержаться в отчете, и **returnValue** значения, указанного в определяемую клиентом функцией отчетов, которое могут быть возвращены **_ CrtDbgReport**. Полное описание доступных типов отчетов см. в описании функции [_CrtSetReportMode](crtsetreportmode.md).

Если определяемая клиентом функция отчетов полностью обрабатывает сообщение отладки, таким образом, что дальнейшая выдача отчета не требуется, функция должна возвращать. **TRUE**. Когда функция возвращает **FALSE**, **_CrtDbgReport** вызывается для формирования отчета об отладке, используя текущие параметры для типа отчета, режима и файла. Кроме того, указав **_CrtDbgReport** возвращаемое значение в **returnValue**, приложение может контролировать, происходит ли прерывание при отладке. Полное описание способа настройки и создания отчета об отладке см. в разделе **_CrtSetReportMode**, [_CrtSetReportFile](crtsetreportfile.md), и **_CrtDbgReport**.

Дополнительные сведения о других допускающих подключение функциях среды выполнения и написании собственных определяемых клиентом функциях-ловушках см. в разделе [Написание функций отладочных ловушек](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> Если приложение компилируется с **/CLR** и функция отчетов вызывается после выхода из приложения main, среда CLR вызывает исключение, если функция отчетов вызывает функции CRT.

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
