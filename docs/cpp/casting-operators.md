---
title: Операторы приведения | Документация Майкрософт
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 341812299d8cf95e351a087e9957dc0425cb25b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075947"
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