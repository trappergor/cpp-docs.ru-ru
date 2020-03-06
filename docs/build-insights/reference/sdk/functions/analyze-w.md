---
title: анализев
description: Справочник C++ по функциям SDK для Build Insights анализев.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bd9b401f08941134d3c267df5c23c5d9e981cb86
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334490"
---
# <a name="analyzew"></a>анализев

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `AnalyzeW` используется для анализа событий КОМПИЛЯТОРОМ MSVC, считанных из трассировки входных данных трассировки событий Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE AnalyzeW(
    const wchar_t*             inputLogFile,
    const ANALYSIS_DESCRIPTOR* analysisDescriptor);
```

### <a name="parameters"></a>Параметры

*инпутлогфиле*\
Входная трассировка ETW, из которой требуется считать события.

*аналисисдескриптор*\
Указатель на объект [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) . Используйте этот объект для настройки анализа.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end
