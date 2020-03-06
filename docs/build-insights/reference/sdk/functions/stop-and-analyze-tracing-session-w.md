---
title: стопанданализетраЦингсессионв
description: Справочник C++ по функциям SDK для Build Insights стопанданализетраЦингсессионв.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ec36162efcd2bfcf17cb07a997a7ff170338d3d2
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334268"
---
# <a name="stopandanalyzetracingsessionw"></a>стопанданализетраЦингсессионв

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopAndAnalyzeTracingSessionW` останавливает текущий сеанс трассировки и сохраняет результирующую трассировку во временном файле. Затем сеанс анализа сразу же запускается с использованием временного файла в качестве входных данных. Исполняемые файлы, вызывающие эту функцию, должны иметь права администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionW(
    const wchar_t*              sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя останавливаемого сеанса трассировки. Используйте то же имя сеанса, что и переданное в [старттраЦингсессион](start-tracing-session.md), [старттраЦингсессиона](start-tracing-session-a.md)или [старттраЦингсессионв](start-tracing-session-w.md).

*статистика*\
Указатель на объект [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopAndAnalyzeTracingSessionW` записывает статистику сбора трассировки в этот объект перед возвратом.

*аналисисдескриптор*\
Указатель на объект [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) . Этот объект используется для настройки сеанса анализа, запускаемого `StopAndAnalyzeTracingSessionW`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end
