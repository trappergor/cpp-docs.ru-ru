---
title: Класс is_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_constructible
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
ms.openlocfilehash: dc0596ac7a3fc2bcbcbe49f5fa4b20a971e5e445
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452864"
---
# <a name="isconstructible-class"></a>Класс is_constructible

Проверяет, является ли тип конструируемым при использовании указанных типов аргументов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

*Args*\
Типы аргументов для сопоставления в конструкторе *T*.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является конструируемым с помощью типов аргументов в аргументах *args*, в противном случае — значение false. Тип *T* — конструируемым, если определение `T t(std::declval<Args>()...);` переменной имеет правильный формат. *T* и все типы в аргументах *args* должны быть полными типами, **void**или массивами неизвестной привязки.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
