---
title: Проверка ошибок во время выполнения
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
ms.openlocfilehash: ec07b9b0c6aa52187c3c24bff4cc51712dbf9fc8
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746465"
---
# <a name="run-time-error-checking"></a>Проверка ошибок во время выполнения

Библиотека времени выполнения C содержит функции, поддерживающие проверку ошибок во время выполнения (RTC). Проверка ошибок во время выполнения позволяет строить программы так, чтобы получать сообщения о некоторых типах ошибок, возникающих во время выполнения. Можно указать, каким образом происходит уведомление об ошибках, а также типы этих ошибок. Дополнительные сведения см. в разделе [Как использовать проверки во время выполнения машинного кода](/visualstudio/debugger/how-to-use-native-run-time-checks).

Для настройки выполнения проверок на ошибки во время выполнения используются следующие функции.

## <a name="run-time-error-checking-functions"></a>Функции проверки на ошибки во время выполнения

|Функция|Использовать|
|--------------|---------|
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Возвращает краткое описание типа проверки на ошибки во время выполнения.|
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Возвращает общее количество ошибок, которые могут быть обнаружены путем проверки во время выполнения.|
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Назначает функцию в качестве обработчика для сообщений о проверке на ошибки во время выполнения.|
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Связывает обнаруженную проверкой во время выполнения ошибку с типом.|

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
[/RTC (проверки ошибок во время выполнения)](../build/reference/rtc-run-time-error-checks.md)<br/>
[runtime_checks](../preprocessor/runtime-checks.md)<br/>
[Процедуры отладки](../c-runtime-library/debug-routines.md)<br/>
