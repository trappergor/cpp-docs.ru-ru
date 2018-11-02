---
title: Класс is_trivially_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: c83bea8be5c88876ffa25337464caa62b998ab45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628843"
---
# <a name="istriviallyconstructible-class"></a>Класс is_trivially_constructible

Проверяет, является ли тип просто создаваемым при использовании указанных типов аргументов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

*Args*<br/>
Типы аргументов для сопоставления в конструктор *T*.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* — просто создаваемый при использовании типов аргументов в *Args*, в противном случае он содержит значение false. Тип *T* является просто создаваемым при определении переменной `T t(std::declval<Args>()...);` имеет правильный формат и известно, что вызов не нетривиальные операции. Оба *T* и все типы в *Args* должны быть полными типами **void**, или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
