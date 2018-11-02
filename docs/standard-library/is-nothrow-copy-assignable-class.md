---
title: Класс is_nothrow_copy_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: bb3aca47b61bdcc5b28eeedc1a6b4edefc303c4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583759"
---
# <a name="isnothrowcopyassignable-class"></a>Класс is_nothrow_copy_assignable

Проверяет, имеет ли тип оператор назначения копии, который известен компилятору как не отбрасываемый.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если для типа с возможностью ссылки *T* где `is_nothrow_assignable<T&, const T&>` содержит значение true; в противном случае он содержит значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_nothrow_assignable](../standard-library/is-nothrow-assignable-class.md)<br/>
