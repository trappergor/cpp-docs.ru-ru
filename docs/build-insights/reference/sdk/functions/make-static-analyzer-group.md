---
title: MakeStaticAnalyzerGroup
description: Ссылка на функцию «СИ Тиз Сборка» SDK MakeStaticAnalyzerGroup.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 72f7f5d7a408436902394451a52dd66efe1d93f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323932"
---
# <a name="makestaticanalyzergroup"></a>MakeStaticAnalyzerGroup

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MakeStaticAnalyzerGroup` используется для создания статической группы анализатора, которая может быть передана таким функциям, как [Анализ](analyze.md) или [Relog.](relog.md) Члены группы анализаторов получают события один за другим слева направо, пока не будут проанализированы все события в следе.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>Параметры

*TAnalyzerPtrs*\
Этот параметр всегда выводится.

*Анализаторы*\
Пакет параметров указателей [IAnalyzer,](../other-types/ianalyzer-class.md) включенных в группу статического анализатора. Эти указатели могут `std::unique_ptr`быть `std::shared_ptr`сырыми, или .

### <a name="return-value"></a>Возвращаемое значение

Статический анализатор группы. Используйте **ключевое** слово auto для захвата значения возврата.

## <a name="remarks"></a>Remarks

В отличие от групп динамических анализаторов, члены группы статического анализатора должны быть известны во время компиляции. Кроме того, группа статического анализатора содержит указатели [IAnalyzer,](../other-types/ianalyzer-class.md) которые не имеют полиморфного поведения. При использовании группы статического анализатора для анализа отслеживания событий `IAnalyzer` для отслеживания событий для Отслеживания событий для Windows (ETW) трассировка интерфейса всегда разрешится объекту, непосредственно на который указывает член группы анализаторов. Эта потеря гибкости обеспечивает возможность более быстрого времени обработки событий. Если члены группы анализаторов не могут быть известны во время компиляции, или если вам требуется полиморфное поведение на указателях, `IAnalyzer` рассмотрите возможность использования группы динамических анализаторов. Чтобы использовать группу динамического анализа, позвоните [в MakeDynamicAnalyzerGroup.](make-static-analyzer-group.md)

::: moniker-end
