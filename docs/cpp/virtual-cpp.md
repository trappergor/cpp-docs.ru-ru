---
title: virtual (C++)
ms.date: 11/04/2016
f1_keywords:
- virtual_cpp
- virtual
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
ms.openlocfilehash: a8948594bade940834e041adc73d56cc7847acc0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187509"
---
# <a name="virtual-c"></a>virtual (C++)

Ключевое слово **Virtual** объявляет виртуальную функцию или виртуальный базовый класс.

## <a name="syntax"></a>Синтаксис

```
virtual [type-specifiers] member-function-declarator
virtual [access-specifier] base-class-name
```

#### <a name="parameters"></a>Параметры

*описатели типа*<br/>
Указывает тип возвращаемого значения виртуальной функции-члена.

*декларатор с функцией-членом*<br/>
Объявляет функцию-член.

*описатель доступа*<br/>
Определяет уровень доступа к базовому классу, **открытому**, **защищенному** или **закрытому**. Может располагаться до или после ключевого слова **Virtual** .

*имя базового класса*<br/>
Определяет ранее объявленный тип класса.

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [виртуальные функции](../cpp/virtual-functions.md) .

Также см. следующие ключевые слова: [класс](../cpp/class-cpp.md), [частный](../cpp/private-cpp.md), [открытый](../cpp/public-cpp.md)и [защищенный](../cpp/protected-cpp.md).

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)
