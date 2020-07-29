---
title: Сведения о типах времени выполнения
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
ms.openlocfilehash: b6d3652539572f094d0e7139e6672402341c956d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232239"
---
# <a name="run-time-type-information"></a>Сведения о типах времени выполнения

Информация о типах времени выполнения (RTTI) — это механизм, позволяющий определить тип объекта во время выполнения программы. Функция RTTI была добавлена в язык C++, поскольку многие поставщики библиотек классов реализовывали ее самостоятельно. Это приводило к проблемам совместимости между библиотеками. Таким образом, стало очевидно, что необходима поддержка информации о типах времени выполнения на уровне языка.

Для ясности этот раздел о RTTI почти полностью посвящен указателям. Однако рассматриваемые понятия также применяются ко ссылкам.

Существует три основных элемента языка C++ для информации о типах времени выполнения.

- Оператор [dynamic_cast](../cpp/dynamic-cast-operator.md) .

   Используется для преобразования полиморфных типов.

- Оператор [typeid](../cpp/typeid-operator.md) .

   Используется для указания точного типа объекта.

- Класс [type_info](../cpp/type-info-class.md) .

   Используется для хранения сведений о типе, возвращаемых **`typeid`** оператором.

## <a name="see-also"></a>См. также раздел

[Приведение](../cpp/casting.md)
