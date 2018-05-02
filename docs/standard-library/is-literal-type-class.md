---
title: Класс is_literal_type | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_literal_type
dev_langs:
- C++
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8779ec9cd956d8f653f12543a9f3c0327d0494d3
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="isliteraltype-class"></a>Класс is_literal_type

Проверяет, можно ли использовать тип в качестве переменной `constexpr`, создавать его, использовать или возвращать из функций `constexpr`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа имеет значение true, если тип `T` является *типом литерала*, в противном случае — значение false. Тип литерала — это `void`, скалярный тип, ссылочный тип, массив типа литерала или тип класса литерала. Тип класса литерала — это тип класса, который имеет тривиальный деструктор, составной тип или по крайней мере один конструктор `constexpr`, отличный от копирования и перемещения, и все его базовые классы и нестатические элементы данных являются неизменяемыми типами литералов. Хотя литерал всегда имеет тип литерала, концепция типа литерала включает в себя все, что компилятор может вычислить в качестве `constexpr` во время компиляции.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
