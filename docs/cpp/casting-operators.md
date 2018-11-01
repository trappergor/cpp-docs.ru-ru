---
title: Операторы приведения
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: 4d6c8a0dc448e08ae2f344faeeb27756cdd27eff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549751"
---
# <a name="casting-operators"></a>Операторы приведения

Некоторые операторы приведения типа используются только в языке C++. Эти операторы позволяют устранить неоднозначность и возможности допустить ошибку, которые характеры для приведения типов в стиле языка C. Эти операторы перечислены ниже.

- [dynamic_cast](../cpp/dynamic-cast-operator.md) используется для преобразования полиморфных типов.

- [static_cast](../cpp/static-cast-operator.md) используется для преобразования неполиморфных типов.

- [const_cast](../cpp/const-cast-operator.md) используется для удаления **const**, **volatile**, и **__unaligned** атрибуты.

- [reinterpret_cast](../cpp/reinterpret-cast-operator.md) для простой повторной интерпретации разрядов.

- [safe_cast](../windows/safe-cast-cpp-component-extensions.md) используется для создания проверяемых MSIL.

Используйте **const_cast** и **reinterpret_cast** в качестве последнего средства, так как же опасностях как приведения старого стиля представления этих операторов. Однако они необходимы, чтобы полностью заменить приведения старого стиля.

## <a name="see-also"></a>См. также

[Приведение](../cpp/casting.md)