---
title: Прагма optimize
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
ms.openlocfilehash: 6d7b99b7a72c133d56a209cf42fa9ef670a4a7f9
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220514"
---
# <a name="optimize-pragma"></a>Прагма optimize

Задает оптимизацию для каждой функции по функциям.

## <a name="syntax"></a>Синтаксис

> **#pragma optimize ("** [ *Оптимизация-List* ] **",** { **On** | **Off** } **)**

## <a name="remarks"></a>Примечания

Директива pragma **optimize** должна находиться за пределами функции. Он вступает в силу в первой функции, определенной после того, как будет показана директива pragma. Параметры включения и **отключения** аргументов, заданные в *списке оптимизация —* on или OFF.

*Оптимизация-список* может быть равен нулю или большему числу параметров, приведенных в следующей таблице.

### <a name="parameters-of-the-optimize-pragma"></a>Параметры директивы #pragma optimize

| Параметры | Тип оптимизации |
|--------------------|--------------------------|
| **g** | Включить глобальную оптимизацию. |
| **s** или **t** | Указывать короткую или быструю последовательность машинного кода. |
| **y** | Создавать указатели фреймов в стеке программы. |

Эти параметры совпадают с буквами, используемыми в параметрах компилятора [/o](../build/reference/o-options-optimize-code.md) . Например, следующая директива #pragma эквивалентна параметру компилятора `/Os`:

```cpp
#pragma optimize( "s", on )
```

Использование директивы pragma **optimize** с пустой строкой ( **""** ) представляет собой специальную форму:

При использовании параметра **Off** происходит включение всех оптимизаций, **g**, **s**, **t**и **y**.

При использовании параметра **On** он сбрасывает оптимизацию до тех, которые были указаны с помощью параметра компилятора [/o](../build/reference/o-options-optimize-code.md) .

```cpp
#pragma optimize( "", off )
/* unoptimized code section */
#pragma optimize( "", on )
```

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
