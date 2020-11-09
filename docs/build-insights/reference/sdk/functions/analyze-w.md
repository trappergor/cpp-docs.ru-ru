---
title: AnalyzeW
description: Справочник по функции AnalyzeW пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a75668e0fc9d356315f5f0b3156a909187415521
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922852"
---
# <a name="analyzew"></a>AnalyzeW

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `AnalyzeW` используется для анализа событий MSVC, считанных из входных данных трассировки событий Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE AnalyzeW(
    const wchar_t*             inputLogFile,
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
