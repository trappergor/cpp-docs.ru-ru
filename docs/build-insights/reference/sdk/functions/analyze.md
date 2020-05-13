---
title: Анализ
description: Ссылка на функцию SDK Build Insights SDK Analyse.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 08b3643270cc785b3fbea36720d192b4a1473104
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324111"
---
# <a name="analyze"></a>Анализ

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `Analyze` используется для анализа отслеживания событий для отслеживания Windows (ETW) трассы, полученной из MSVC во время отслеживания сборки C. События в следе ETW последовательно перенаправляются группе анализаторов, предоставленной абонентом. Эта функция поддерживает многопроходный анализ, который позволяет перенаправить поток событий в группу анализаторов несколько раз подряд.

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

*TAnalyzerGroupЧлены*\
Этот параметр всегда выводится.

*вхотливыйLogFile*\
Входный след ETW, из которого вы хотите прочитать события.

*numberOfPasses*\
Количество анализов проходит для выполнения на входе следа. След проходит через предоставленную группу анализаторов один раз за анализ.

*анализаторГруппа*\
Группа анализаторов, используемая для анализа. Позвоните [MakeStaticAnalyzerGroup,](make-static-analyzer-group.md) чтобы создать группу анализаторов. Чтобы использовать группу динамического анализатора, полученную от [MakeDynamicAnalyzerGroup,](make-dynamic-analyzer-group.md)сначала инкапсулируют `MakeStaticAnalyzerGroup`его внутри группы статического анализатора, передав его адрес .

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

::: moniker-end
