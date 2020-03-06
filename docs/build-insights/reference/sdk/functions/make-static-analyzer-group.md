---
title: макестатиканализерграуп
description: Справочник C++ по функциям SDK для Build Insights макестатиканализерграуп.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5eabb0fcbb0a0bb0eea0f4e6bbf27b8e4c53c3ab
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334394"
---
# <a name="makestaticanalyzergroup"></a>макестатиканализерграуп

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MakeStaticAnalyzerGroup` используется для создания статической группы анализатора, которая может быть передана таким функциям, как [Analyze](analyze.md) или [Relog](relog.md). Члены группы анализатора получают события по одному слева направо, пока не будут проанализированы все события в трассировке.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>Параметры

*Танализерптрс*\
Этот параметр всегда выводится.

*анализаторы*\
Пакет параметров [ианализер](../other-types/ianalyzer-class.md) указателей, включаемых в статическую группу анализатора. Эти указатели могут быть необработанными, `std::unique_ptr`или `std::shared_ptr`.

### <a name="return-value"></a>Возвращаемое значение

Статическая группа анализатора. Используйте ключевое слово **Auto** для записи возвращаемого значения.

## <a name="remarks"></a>Remarks

В отличие от динамических групп анализатора, члены статической группы анализатора должны быть известны во время компиляции. Кроме того, статическая группа анализатора содержит [ианализер](../other-types/ianalyzer-class.md) указатели, которые не имеют полиморфизма. При использовании статической группы анализатора для анализа трассировки трассировки событий Windows (ETW) вызовы интерфейса `IAnalyzer` всегда разрешаются в объект, непосредственно указываемый элементом группы анализатора. Такая утрата гибкости связана с возможностью ускорения обработки событий. Если члены группы анализатора не могут быть известны во время компиляции или требуется полиморфизм на `IAnalyzer`ных указателях, рассмотрите возможность использования динамической группы анализатора. Чтобы использовать группу динамического анализатора, вызовите [макединамиканализерграуп](make-static-analyzer-group.md) .

::: moniker-end
