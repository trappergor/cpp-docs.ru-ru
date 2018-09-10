---
title: Класс is_literal_type | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_literal_type
dev_langs:
- C++
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd4481be124cbcbba04f6b45b4c5a08beb34f04d
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103309"
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
