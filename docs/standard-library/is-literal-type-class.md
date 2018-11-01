---
title: Класс is_literal_type
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: 804ef0462308b967fc0c4c95d8dfa96476475aab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514010"
---
# <a name="isliteraltype-class"></a>Класс is_literal_type

Проверяет, можно ли использовать тип в качестве переменной `constexpr`, создавать его, использовать или возвращать из функций `constexpr`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* — *типа литерала*, в противном случае он содержит значение false. Тип литерала — это либо **void**, скалярный тип, ссылочный тип, массив типа литерала или тип класса литерала. Тип класса литерала — это тип класса, который имеет тривиальный деструктор, составной тип или по крайней мере один конструктор `constexpr`, отличный от копирования и перемещения, и все его базовые классы и нестатические элементы данных являются неизменяемыми типами литералов. Хотя литерал всегда имеет тип литерала, концепция типа литерала включает в себя все, что компилятор может вычислить в качестве `constexpr` во время компиляции.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
