---
title: StartTracingSessionA
description: Справочник по функции StartTracingSessionA пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 388ccbe58ab5cc59d995601536a2034e847e2e1d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920012"
---
# <a name="starttracingsessiona"></a>StartTracingSessionA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `StartTracingSessionA` запускает сеанс трассировки. Исполняемые файлы, вызывающие эту функцию, должны иметь привилегии администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StartTracingSessionA(
    const char*                    sessionName,
    const TRACING_SESSION_OPTIONS* options);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя запускаемого сеанса трассировки. Используйте то же имя при вызове [StopTracingSessionA](stop-tracing-session.md) или любой другой функции для остановки трассировки.

*options*\
Указатель на объект [TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md). Этот объект используется для выбора событий, собираемых во время сеанса трассировки.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

::: moniker-end
