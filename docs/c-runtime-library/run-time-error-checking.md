---
title: Проверка ошибок во время выполнения
ms.date: 11/04/2016
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
ms.openlocfilehash: cf707cbd53e2285684d53d3f440db0f618343598
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444832"
---
# <a name="run-time-error-checking"></a>Проверка ошибок во время выполнения

Библиотека времени выполнения C содержит функции, поддерживающие проверку ошибок во время выполнения (RTC). Проверка ошибок во время выполнения позволяет строить программы так, чтобы получать сообщения о некоторых типах ошибок, возникающих во время выполнения. Можно указать, каким образом происходит уведомление об ошибках, а также типы этих ошибок. Дополнительная информация есть в статье [Практическое руководство. Настройка проверок во время выполнения машинного кода](/visualstudio/debugger/how-to-use-native-run-time-checks).

Для настройки выполнения проверок на ошибки во время выполнения используются следующие функции.

## <a name="run-time-error-checking-functions"></a>Функции проверки на ошибки во время выполнения

|Компонент|Использование|
|--------------|---------|
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Возвращает краткое описание типа проверки на ошибки во время выполнения.|
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Возвращает общее количество ошибок, которые могут быть обнаружены путем проверки во время выполнения.|
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Назначает функцию в качестве обработчика для сообщений о проверке на ошибки во время выполнения.|
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Связывает обнаруженную проверкой во время выполнения ошибку с типом.|

## <a name="see-also"></a>См. также раздел

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
[/RTC (проверки ошибок во время выполнения)](../build/reference/rtc-run-time-error-checks.md)<br/>
[runtime_checks](../preprocessor/runtime-checks.md)<br/>
[Процедуры отладки](../c-runtime-library/debug-routines.md)<br/>
