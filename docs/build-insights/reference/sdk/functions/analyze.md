---
title: Анализ
description: Справочник C++ по функциям анализа пакета SDK для аналитики сборки.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 49161641d1cff1c64261d95bb2caace2f802543a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334436"
---
# <a name="analyze"></a>Анализ

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `Analyze` используется для анализа трассировки трассировки событий Windows (ETW), полученной из КОМПИЛЯТОРОМ MSVC при трассировке C++ сборки. События в трассировке ETW пересылаются последовательно в группу анализатора, предоставленную вызывающей стороной. Эта функция поддерживает многопроходный анализ, который позволяет пересылать поток событий в группу анализатора несколько раз в строке.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const char*                                   inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const wchar_t*                                inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>Параметры

*Танализерграупмемберс*\
Этот параметр всегда выводится.

*инпутлогфиле*\
Входная трассировка ETW, из которой требуется считать события.

*нумберофпассес*\
Количество проходов анализа для выполнения во входной трассировке. Трассировка передается через предоставленную группу анализаторов один раз для каждого этапа анализа.

*анализерграуп*\
Группа анализаторов, используемая для анализа. Вызовите [макестатиканализерграуп](make-static-analyzer-group.md) , чтобы создать группу анализатора. Чтобы использовать группу динамического анализатора, полученную из [макединамиканализерграуп](make-dynamic-analyzer-group.md), сначала необходимо инкапсулировать ее в статическую группу анализатора, передав ее адрес в `MakeStaticAnalyzerGroup`.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end
