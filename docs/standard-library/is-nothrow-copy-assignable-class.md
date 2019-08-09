---
title: Класс is_nothrow_copy_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: 330c97cd945e161d2bf47deb377dd732bf53b3c9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455981"
---
# <a name="isnothrowcopyassignable-class"></a>Класс is_nothrow_copy_assignable

Проверяет, имеет ли тип оператор назначения копии, который известен компилятору как не отбрасываемый.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true для ссылочного типа *T* , где `is_nothrow_assignable<T&, const T&>` имеет значение true; в противном случае — значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[Класс is_nothrow_assignable](../standard-library/is-nothrow-assignable-class.md)
