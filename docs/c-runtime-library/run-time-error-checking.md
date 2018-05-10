---
title: Проверка ошибок во время выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2468cd05efdf732fbf955b8532a61d24fa6c0ff4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="run-time-error-checking"></a>Проверка ошибок во время выполнения

Библиотека времени выполнения C содержит функции, поддерживающие проверку ошибок во время выполнения (RTC). Проверка ошибок во время выполнения позволяет строить программы так, чтобы получать сообщения о некоторых типах ошибок, возникающих во время выполнения. Можно указать, каким образом происходит уведомление об ошибках, а также типы этих ошибок. Дополнительная информация есть в статье [Практическое руководство. Настройка проверок во время выполнения машинного кода](/visualstudio/debugger/how-to-use-native-run-time-checks).

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
