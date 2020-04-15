---
title: MakeDynamicReloggerGroup
description: Ссылка на функцию «Исследования сборки» SDK MakeDynamicReloggerGroup.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f49e37f8e1a8b9ca9a800d20b2891a54453095ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323954"
---
# <a name="makedynamicreloggergroup"></a>MakeDynamicReloggerGroup

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MakeDynamicReloggerGroup` используется для создания динамической группы перелоггеров. Члены группы relogger получают события один за другим слева направо до тех пор, пока не будут обработаны все события в следе.

## <a name="syntax"></a>Синтаксис

```cpp
auto MakeDynamicReloggerGroup(std::vector<IRelogger*> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::shared_ptr<IRelogger>> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::unique_ptr<IRelogger>> reloggers);
```

### <a name="parameters"></a>Параметры

*перелоггеры*\
Вектор указателей [IRelogger,](../other-types/irelogger-class.md) включенных в динамическую группу релоггеров. Эти указатели могут `std::unique_ptr`быть `std::shared_ptr`сырыми, или . [Указатели IAnalyzer](../other-types/ianalyzer-class.md) также `IRelogger` считаются указатели из-за отношения наследования.

### <a name="return-value"></a>Возвращаемое значение

Динамическая группа релоггеров. Используйте **ключевое** слово auto для захвата значения возврата.

## <a name="remarks"></a>Remarks

В отличие от статических групп перелоггеров, члены динамической группы перелоггеров не должны быть известны во время компиляции. Вы можете выбрать участников группы relogger во время выполнения на основе ввода программы или на основе других значений, неизвестных во время компиляции. В отличие от статических групп релоггеров, указатели [IRelogger](../other-types/irelogger-class.md) в группе динамических перелогов имеют полиморфное поведение, и виртуальные вызовы функции отправляются правильно. Эта гибкость обеспечивается за счет возможного замедления времени обработки событий. Когда все участники группы relogger известны во время компиляции, и если вам не нужно полиморфное поведение, подумайте об использовании статической группы перелогов. Чтобы использовать статическую группу перелога, позвоните [makeStaticReloggerGroup.](make-static-relogger-group.md)

Динамическая группа релоггеров может быть инкапсулирована внутри статической группы релоггеров. Вы передаете свой адрес [MakeStaticReloggerGroup.](make-static-relogger-group.md) Используйте этот метод для передачи динамических групп перелоггера таким функциям, как [Relog,](relog.md)которые принимают только статические группы перелога.

::: moniker-end
