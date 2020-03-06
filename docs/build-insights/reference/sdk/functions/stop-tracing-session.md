---
title: стоптраЦингсессион
description: Справочник C++ по функциям SDK для Build Insights стоптраЦингсессион.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a4be229dcfddef0624869b789ee35e51336ac78e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334166"
---
# <a name="stoptracingsession"></a>стоптраЦингсессион

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopTracingSession` останавливает текущий сеанс трассировки и создает необработанный файл трассировки. Необработанные файлы трассировки могут быть переданы функциям [Analyze](analyze.md), [аналзеа](analyze-a.md)и [анализев](analyze-w.md) для запуска сеанса анализа. Необработанные файлы трассировки также могут передаваться в функции [Relog](relog.md), [релога](relog-a.md)и [релогв](relog-w.md) для запуска сеанса повторного ведения журнала. Исполняемые файлы, вызывающие `StopTracingSession`, должны иметь права администратора.

## <a name="syntax"></a>Синтаксис

```cpp
inline RESULT_CODE StopTracingSession(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);

inline RESULT_CODE StopTracingSession(
    const wchar_t*              sessionName
    const wchar_t*              outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, что и переданное в [старттраЦингсессион](start-tracing-session.md), [старттраЦингсессиона](start-tracing-session-a.md)или [старттраЦингсессионв](start-tracing-session-w.md).

*аутпутлогфиле*\
Путь к окончательному выходному файлу журнала, в котором должна быть сохранена необработанная трассировка.

*статистика*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopTracingSession` записывает статистику сбора трассировки в этот объект перед возвратом.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end
