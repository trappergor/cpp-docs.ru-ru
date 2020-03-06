---
title: стоптраЦингсессиона
description: Справочник C++ по функциям SDK для Build Insights стоптраЦингсессиона.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 12f0c7a9665c47f36fb5e88d799673918017bb98
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334196"
---
# <a name="stoptracingsessiona"></a>стоптраЦингсессиона

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopTracingSessionA` останавливает текущий сеанс трассировки и создает необработанный файл трассировки. Необработанные файлы трассировки могут быть переданы функциям [Analyze](analyze.md), [аналзеа](analyze-a.md)и [анализев](analyze-w.md) для запуска сеанса анализа. Необработанные файлы трассировки могут также передаваться функциям [Relog](relog.md), [релога](relog-a.md)и [релогв](relog-w.md) для запуска сеанса повторного ведения журнала. Исполняемые файлы, вызывающие `StopTracingSessionA`, должны иметь права администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StopTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, что и переданное в [старттраЦингсессион](start-tracing-session.md), [старттраЦингсессиона](start-tracing-session-a.md)или [старттраЦингсессионв](start-tracing-session-w.md).

*аутпутлогфиле*\
Путь к окончательному выходному файлу журнала, в котором должна быть сохранена необработанная трассировка.

*статистика*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopTracingSessionA` записывает статистику сбора трассировки в этот объект перед возвратом.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end
