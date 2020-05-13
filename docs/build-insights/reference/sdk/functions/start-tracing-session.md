---
title: StartTracingSession
description: Ссылка на функцию «Си Видоанализс SDK StartTracingSession».
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6da81ce54948e5ddbacfc9af50f1be12736fdba7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323739"
---
# <a name="starttracingsession"></a>StartTracingSession

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StartTracingSession` запускает сеанс отслеживания. Исполнители вызова этой функции должны иметь привилегии администратора.

## <a name="syntax"></a>Синтаксис

```cpp
RESULT_CODE StartTracingSession(
    const char*                    sessionName,
    const TRACING_SESSION_OPTIONS& options);

RESULT_CODE StartTracingSession(
    const wchar_t*                 sessionName,
    const TRACING_SESSION_OPTIONS& options);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Название сеанса отслеживания для начала. Используйте одно и то же имя при [вызове StopTracingSession](stop-tracing-session.md) или любой другой функции стоп-следа.

*Параметры*\
Указатель на [TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md) объект. Используйте этот объект, чтобы выбрать, какие события должны быть собраны сеансом отслеживания.

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

::: moniker-end
