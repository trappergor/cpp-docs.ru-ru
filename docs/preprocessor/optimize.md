---
title: optimize
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
ms.openlocfilehash: 65948f2b466bdd40bd753dbba99e2e235c57b0f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615869"
---
# <a name="optimize"></a>optimize

Задает оптимизации, которые требуется выполнять для каждой функции.

## <a name="syntax"></a>Синтаксис

```
#pragma optimize( "[optimization-list]", {on | off} )
```

## <a name="remarks"></a>Примечания

**Оптимизировать** директива pragma должна находиться за пределами функции и вступает в силу в первой функции, определенной после этой директивы #pragma. *На* и *off* аргументы включить параметры, указанные в *списке оптимизации* или отключить.

*Списке оптимизации* может содержать ноль или несколько параметров, приведенных в следующей таблице.

### <a name="parameters-of-the-optimize-pragma"></a>Параметры директивы #pragma optimize

|Параметры|Тип оптимизации|
|--------------------|--------------------------|
|*g*|Включить глобальную оптимизацию.|
|*s* или *t*|Указывать короткую или быструю последовательность машинного кода.|
|*y*|Создавать указатели фреймов в стеке программы.|

Это же буквы используются с [/O](../build/reference/o-options-optimize-code.md) параметры компилятора. Например, следующая директива #pragma эквивалентна параметру компилятора `/Os`:

```
#pragma optimize( "ts", on )
```

С помощью **оптимизировать** pragma с пустой строкой (**«»**) представляет собой специальную форму директивы:

При использовании *off* параметр, он включает все оптимизации, *g*, *s*, *t*, и *y*, off.

При использовании *на* параметр, она снова устанавливает оптимизации указанных с помощью [/O](../build/reference/o-options-optimize-code.md) параметр компилятора.

```
#pragma optimize( "", off )
.
.
.
#pragma optimize( "", on )
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)