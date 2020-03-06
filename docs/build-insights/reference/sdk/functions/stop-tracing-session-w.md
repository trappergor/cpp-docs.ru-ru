---
title: стоптраЦингсессионв
description: Справочник C++ по функциям SDK для Build Insights стоптраЦингсессионв.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fbb31b600d6aee8c03cb0b52f71c0afcb8b8e3b3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334172"
---
# <a name="stoptracingsessionw"></a>стоптраЦингсессионв

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopTracingSessionW` останавливает текущий сеанс трассировки и создает необработанный файл трассировки. Необработанные файлы трассировки могут быть переданы функциям [Analyze](analyze.md), [аналзеа](analyze-a.md)и [анализев](analyze-w.md) для запуска сеанса анализа. Необработанные файлы трассировки могут также передаваться функциям [Relog](relog.md), [релога](relog-a.md)и [релогв](relog-w.md) для запуска сеанса повторного ведения журнала. Исполняемые файлы, вызывающие `StopTracingSessionW`, должны иметь права администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StopTracingSessionW(
    const wchar_t*              sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, что и переданное в [старттраЦингсессион](start-tracing-session.md), [старттраЦингсессиона](start-tracing-session-a.md)или [старттраЦингсессионв](start-tracing-session-w.md).

*аутпутлогфиле*\
Путь к окончательному выходному файлу журнала, в котором должна быть сохранена необработанная трассировка.

*статистика*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopTracingSessionW` записывает статистику сбора трассировки в этот объект перед возвратом.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end
