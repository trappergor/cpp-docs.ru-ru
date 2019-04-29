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
ms.openlocfilehash: f68bd2e500ebe16c43ef6c3d7a5aede26421b27d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393913"
---
# <a name="virtual-c"></a>virtual (C++)

**Виртуального** ключевое слово объявляет виртуальную функцию или виртуальный базовый класс.

## <a name="syntax"></a>Синтаксис

```
virtual [type-specifiers] member-function-declarator
virtual [access-specifier] base-class-name
```

#### <a name="parameters"></a>Параметры

*Спецификаторы типов*<br/>
Указывает тип возвращаемого значения виртуальной функции-члена.

*объявление члена функция*<br/>
Объявляет функцию-член.

*спецификатор доступа*<br/>
Определяет уровень доступа для базового класса, **открытый**, **защищенные** или **частного**. Может отображаться до или после **виртуального** ключевое слово.

*Base имя класса*<br/>
Определяет ранее объявленный тип класса.

## <a name="remarks"></a>Примечания

См. в разделе [виртуальные функции](../cpp/virtual-functions.md) Дополнительные сведения.

Также см. следующие ключевые слова: [класс](../cpp/class-cpp.md), [частного](../cpp/private-cpp.md), [открытый](../cpp/public-cpp.md), и [защищенные](../cpp/protected-cpp.md).

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)