---
title: Операторы приведения
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: 606e8b159bb7bdb7527d33a5211cb33a26913754
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221826"
---
# <a name="casting-operators"></a>Операторы приведения

Некоторые операторы приведения типа используются только в языке C++. Эти операторы позволяют устранить неоднозначность и возможности допустить ошибку, которые характеры для приведения типов в стиле языка C. Эти операторы перечислены ниже.

- [dynamic_cast](../cpp/dynamic-cast-operator.md) Используется для преобразования полиморфизма типов.

- [static_cast](../cpp/static-cast-operator.md) Используется для преобразования типов нонполиморфик.

- [const_cast](../cpp/const-cast-operator.md) Используется для удаления **`const`** атрибутов, **`volatile`** и **`__unaligned`** .

- [reinterpret_cast](../cpp/reinterpret-cast-operator.md) Используется для простой повторной интерпретации битов.

- [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) Используется в C++/CLI для создания проверяемого MSIL.

Используйте **`const_cast`** и **`reinterpret_cast`** в качестве последнего средства, так как эти операторы представляют те же опасности, что и старые преобразования в стиле. Однако они необходимы, чтобы полностью заменить приведения старого стиля.

## <a name="see-also"></a>См. также раздел

[Приведение](../cpp/casting.md)
