---
title: MakeStaticReloggerGroup
description: Ссылка на функцию «Исследования сборки SDK MakeStaticReloggerGroup» .
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75b638537cb8e0cdeeb5476a3f5277e8e90d9baf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323912"
---
# <a name="makestaticreloggergroup"></a>MakeStaticReloggerGroup

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MakeStaticReloggerGroup` используется для создания статической группы перелоггера, которая может быть передана таким функциям, как [Relog.](relog.md) Члены группы relogger получают события один за другим слева направо до тех пор, пока не будут обработаны все события в следе.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename... TReloggerPtrs>
auto MakeStaticReloggerGroup(TReloggerPtrs... reloggers);
```

### <a name="parameters"></a>Параметры

*TReloggerPtrs*\
Этот параметр всегда выводится.

*перелоггеры*\
Параметр пакет [указателей IRelogger,](../other-types/irelogger-class.md) который включен в статическую группу перелоггеров. Эти указатели могут `std::unique_ptr`быть `std::shared_ptr`сырыми, или . [Указатели IAnalyzer](../other-types/ianalyzer-class.md) также `IRelogger` считаются указатели из-за отношения наследования.

### <a name="return-value"></a>Возвращаемое значение

Статическая группа перелоггеров. Используйте **ключевое** слово auto для захвата значения возврата.

## <a name="remarks"></a>Remarks

В отличие от динамических групп перелоггеров, члены группы статического перелога должны быть известны во время компиляции. Кроме того, статическая группа перелогчера содержит указатели [IRelogger,](../other-types/irelogger-class.md) которые не имеют полиморфного поведения. При использовании статической группы перелогов для анализа отслеживания событий для `IRelogger` отслеживания событий для Отслеживания событий для Windows (ETW) след, вызовы в интерфейс всегда разрешаются объекту, непосредственно на который указывает член группы relogger. Эта потеря гибкости обеспечивает возможность более быстрого времени обработки событий. Если члены группы relogger не могут быть известны во время компиляции, `IRelogger` или если вам требуется полиморфное поведение на указателях, рассмотрите возможность использования динамической группы перелоггеров. Вы можете использовать динамическую группу перелогов, позвонив вместо этого по телефону [MakeDynamicReloggerGroup.](make-dynamic-relogger-group.md)

::: moniker-end
