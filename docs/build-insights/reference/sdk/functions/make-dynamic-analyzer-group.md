---
title: MakeDynamicAnalyzerGroup
description: Ссылка на функцию «Си- Сборка» SDK MakeDynamicAnalyzerGroup.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 148eeea41f29ac6dd75653feed7f3f3f8c301911
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323963"
---
# <a name="makedynamicanalyzergroup"></a>MakeDynamicAnalyzerGroup

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MakeDynamicAnalyzerGroup` используется для создания динамической группы анализаторов. Члены группы анализаторов получают события один за другим слева направо, пока не будут проанализированы все события в следе.

## <a name="syntax"></a>Синтаксис

```cpp
auto MakeDynamicAnalyzerGroup(std::vector<IAnalyzer*> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::shared_ptr<IAnalyzer>> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::unique_ptr<IAnalyzer>> analyzers);
```

### <a name="parameters"></a>Параметры

*Анализаторы*\
Вектор указателей [IAnalyzer](../other-types/ianalyzer-class.md) включен в группу динамических анализаторов. Эти указатели могут `std::unique_ptr`быть `std::shared_ptr`сырыми, или .

### <a name="return-value"></a>Возвращаемое значение

Группа динамических анализаторов. Используйте **ключевое** слово auto для захвата значения возврата.

## <a name="remarks"></a>Remarks

В отличие от групп статического анализатора, члены группы динамических анализаторов не должны быть известны во время компиляции. Вы можете выбрать участников группы анализаторов во время выполнения на основе ввода программы или на основе других значений, неизвестных во время компиляции. В отличие от групп статических анализаторов, указатели [IAnalyzer](../other-types/ianalyzer-class.md) в группе динамических анализаторов имеют полиморфное поведение, и виртуальные вызовы функции отправляются правильно. Эта гибкость обеспечивается за счет возможного замедления времени обработки событий. Когда все члены группы анализаторов известны во время компиляции, и если вам не нужно полиморфное поведение, подумайте об использовании группы статического анализатора. Чтобы использовать группу статического анализатора, позвоните в [MakeStaticAnalyzerGroup.](make-static-analyzer-group.md)

Группа динамического анализатора может быть инкапсулирована внутри группы статического анализатора. Это делается, передавая свой адрес [MakeStaticAnalyzerGroup](make-static-analyzer-group.md). Используйте этот метод для передачи динамических групп анализаторов к таким функциям, как [анализ,](analyze.md)которые принимают только статические группы анализаторов.

::: moniker-end
