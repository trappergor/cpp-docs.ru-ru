---
title: Класс is_nothrow_default_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_default_constructible
helpviewer_keywords:
- is_nothrow_default_constructible
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
ms.openlocfilehash: d635c8a06d3acc45d214dbe7cb1eb7800f56dc86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148488"
---
# <a name="isnothrowdefaultconstructible-class"></a>Класс is_nothrow_default_constructible

Проверяет, есть ли у типа невызывающий конструктор по умолчанию.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_nothrow_default_constructible;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* имеет nothrow конструктор по умолчанию, в противном случае он содержит значение false. Экземпляр предиката типа эквивалентен `is_nothrow_constructible<Ty>`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
