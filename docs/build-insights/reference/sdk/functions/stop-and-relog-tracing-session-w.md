---
title: стопандрелогтраЦингсессионв
description: Справочник C++ по функциям SDK для Build Insights стопандрелогтраЦингсессионв.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 021ea5986714fa3432ab6e2831c6069356f380d5
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334208"
---
# <a name="stopandrelogtracingsessionw"></a>стопандрелогтраЦингсессионв

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopAndRelogTracingSessionW` останавливает текущий сеанс трассировки и сохраняет результирующую трассировку во временном файле. Затем сеанс повторного ведения журнала сразу же запускается с использованием временного файла в качестве входных данных. Окончательная трассировка с регистрацией, созданная сеансом перезаписи, сохраняется в файле, указанном вызывающим объектом. Исполняемые файлы, вызывающие эту функцию, должны иметь права администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StopAndRelogTracingSessionW(
    const wchar_t*              sessionName,
    const wchar_t*              outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, что и переданное в [старттраЦингсессион](start-tracing-session.md), [старттраЦингсессиона](start-tracing-session-a.md)или [старттраЦингсессионв](start-tracing-session-w.md).

*аутпутлогфиле*\
Файл, в который записывается Записанная в журнал трассировка, созданная сеансом повторного ведения журнала.

*статистика*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopAndRelogTracingSessionW` записывает статистику сбора трассировки в этот объект перед возвратом.

*аналисисдескриптор*\
Указатель на объект [RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) . Используйте этот объект для настройки сеанса повторного ведения журнала, который запускается `StopAndRelogTracingSessionW`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end
