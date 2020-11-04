---
title: MakeStaticAnalyzerGroup
description: Справочник по функциям пакета средств разработки C++ MakeStaticAnalyzerGroup для аналитики сборки.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d7ddb8652400438c38882b1d27e635e8f1e8db51
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920246"
---
# <a name="makestaticanalyzergroup"></a>MakeStaticAnalyzerGroup

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `MakeStaticAnalyzerGroup` используется для создания статической группы анализаторов, которую можно передать в такие функции, как [`Analyze`](analyze.md) или [`Relog`](relog.md). Члены группы анализаторов получают события по одному слева направо, пока не будут проанализированы все события в трассировке.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>Параметры

*TAnalyzerPtrs*\
Этот параметр выводится во всех случаях.

*analyzers*\
Пакет параметров для указателей [`IAnalyzer`](../other-types/ianalyzer-class.md), включенных в статическую группу анализаторов. Эти указатели могут иметь следующий формат: необработанный, `std::unique_ptr` или `std::shared_ptr`.

### <a name="return-value"></a>Возвращаемое значение

Статическая группа анализаторов. Используйте ключевое слово **`auto`** для захвата возвращаемого значения.

## <a name="remarks"></a>Remarks

В отличие от динамических групп анализаторов, элементы статической группы анализаторов должны быть известны во время компиляции. Кроме того, статическая группа анализаторов содержит указатели [`IAnalyzer`](../other-types/ianalyzer-class.md), которые не имеют полиморфизма. При использовании статической группы анализаторов для анализа трассировки событий Windows (ETW) вызовы к интерфейсу `IAnalyzer` всегда будут разрешаться в объект, на который непосредственно указывает элемент группы анализаторов. Такая утрата гибкости связана с возможностью ускоренной обработки событий. Если элементы группы анализаторов неизвестны во время компиляции или требуется полиморфизм для указателей `IAnalyzer`, рекомендуется использовать динамическую группу анализаторов. Чтобы использовать динамическую группу анализаторов, вызовите [`MakeDynamicAnalyzerGroup`](make-static-analyzer-group.md).

::: moniker-end
