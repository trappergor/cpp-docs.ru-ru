---
title: StopTracingSession
description: Ссылка на функцию «Си- Сборка» SDK StopTracingSession.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c6c7a3c6ca47749491774cc3bcd97aae8aa663ea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323517"
---
# <a name="stoptracingsession"></a>StopTracingSession

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopTracingSession` останавливает текущий сеанс отслеживания и производит необработанный файл трассировки. Сырые файлы трассировки могут быть переданы в [функции Analyse,](analyze.md) [AnalzeA](analyze-a.md)и [AnalyseW](analyze-w.md) для начала сеанса анализа. Сырые файлы трассировки также могут быть переданы функциям [Relog,](relog.md) [RelogA](relog-a.md)и [RelogW](relog-w.md) для начала сеанса повторного заработка. Исполнительные вызовы `StopTracingSession` должны иметь привилегии администратора.

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
Название сеанса отслеживания, чтобы остановить. Используйте то же имя сеанса, что и имя, которое было передано [StartTracingSession,](start-tracing-session.md) [StartTracingSessionA](start-tracing-session-a.md)или [StartTracingSessionW.](start-tracing-session-w.md)

*выходНопок*\
Путь к файлу окончательного вывода журнала, где следует сохранить необработанный след.

*Статистика*\
Указатель на [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) объект. `StopTracingSession`записывает статистику сбора следов на этом объекте перед возвращением.

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

::: moniker-end
