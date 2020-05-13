---
title: StopandAnalyzeTracingSessionw
description: Ссылка на функцию «СИ Тиз» build Insights SDK StopAndAnalyzeTracingSessionW.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2f5f232c3e58c66bc36099d954d97a8f945187ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323722"
---
# <a name="stopandanalyzetracingsessionw"></a>StopandAnalyzeTracingSessionw

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopAndAnalyzeTracingSessionW` останавливает текущий сеанс отслеживания и сохраняет полученный след во временном файле. Затем сеанс анализа немедленно начинает использовать временный файл в качестве ввода. Исполнители вызова этой функции должны иметь привилегии администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionW(
    const wchar_t*              sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Название сеанса отслеживания, чтобы остановить. Используйте то же имя сеанса, что и имя, которое было передано [StartTracingSession,](start-tracing-session.md) [StartTracingSessionA](start-tracing-session-a.md)или [StartTracingSessionW.](start-tracing-session-w.md)

*Статистика*\
Указатель на [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) объект. `StopAndAnalyzeTracingSessionW`записывает статистику сбора следов на этом объекте перед возвращением.

*анализДескриптор*\
Указатель на [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) объект. Используйте этот объект для настройки сеанса `StopAndAnalyzeTracingSessionW`анализа, начатый .

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

::: moniker-end
