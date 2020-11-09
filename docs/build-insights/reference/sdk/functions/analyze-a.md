---
title: AnalyzeA
description: Справочник по функции AnalyzeA пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a2b014c35c2ebc6096b97dd3c0f86bd57e293451
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920311"
---
# <a name="analyzea"></a>AnalyzeA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `AnalyzeA` используется для анализа событий MSVC, считанных из входных данных трассировки событий Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE AnalyzeA(
    const char*                inputLogFile,
    const ANALYSIS_DESCRIPTOR* analysisDescriptor);
```

### <a name="parameters"></a>Параметры

*inputLogFile*\
Входная трассировка ETW, из которой нужно считать события.

*analysisDescriptor*\
Указатель на объект [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md). Используйте этот объект для настройки анализа.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

::: moniker-end
