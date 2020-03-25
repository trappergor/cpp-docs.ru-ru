---
title: Операторы приведения
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: eac274a0207be675b8d13532c3110c6e71bd55c9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190108"
---
# <a name="casting-operators"></a>Операторы приведения

Некоторые операторы приведения типа используются только в языке C++. Эти операторы позволяют устранить неоднозначность и возможности допустить ошибку, которые характеры для приведения типов в стиле языка C. Эти операторы перечислены ниже.

- [dynamic_cast](../cpp/dynamic-cast-operator.md) Используется для преобразования полиморфизма типов.

- [static_cast](../cpp/static-cast-operator.md) Используется для преобразования типов нонполиморфик.

- [const_cast](../cpp/const-cast-operator.md) Используется для удаления атрибутов **const**, **volatile**и **__unaligned** .

- [reinterpret_cast](../cpp/reinterpret-cast-operator.md) Используется для простой повторной интерпретации битов.

- [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) Используется в C++/CLI для создания проверяемого MSIL.

В качестве последнего средства следует использовать **const_cast** и **reinterpret_cast** , так как эти операторы представляют те же опасности, что и старые приведения в стиле. Однако они необходимы, чтобы полностью заменить приведения старого стиля.

## <a name="see-also"></a>См. также раздел

[Приведение](../cpp/casting.md)
