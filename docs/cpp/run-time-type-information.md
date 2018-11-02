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
ms.openlocfilehash: 1d11ee3ea472f935120c59f0faefee905361ee97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656169"
---
# <a name="run-time-type-information"></a>Сведения о типах времени выполнения

Информация о типах времени выполнения (RTTI) — это механизм, позволяющий определить тип объекта во время выполнения программы. Функция RTTI была добавлена в язык C++, поскольку многие поставщики библиотек классов реализовывали ее самостоятельно. Это приводило к проблемам совместимости между библиотеками. Таким образом, стало очевидно, что необходима поддержка информации о типах времени выполнения на уровне языка.

Для ясности этот раздел о RTTI почти полностью посвящен указателям. Однако рассматриваемые понятия также применяются ко ссылкам.

Существует три основных элемента языка C++ для информации о типах времени выполнения.

- [Dynamic_cast](../cpp/dynamic-cast-operator.md) оператор.

   Используется для преобразования полиморфных типов.

- [Typeid](../cpp/typeid-operator.md) оператор.

   Используется для указания точного типа объекта.

- [Type_info](../cpp/type-info-class.md) класса.

   Используется для хранения сведений, возвращаемых методом **typeid** оператор.

## <a name="see-also"></a>См. также

[Приведение](../cpp/casting.md)