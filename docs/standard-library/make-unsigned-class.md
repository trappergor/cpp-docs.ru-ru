---
title: Класс make_unsigned
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 4c0224bd5fd7dc8c6589ae474bb9acb9a8f09cf6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456323"
---
# <a name="makeunsigned-class"></a>Класс make_unsigned

Создает тип или наименьший беззнаковый тип, размер которого больше или равен размеру типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*T*|Тип для изменения.|

## <a name="remarks"></a>Примечания

Экземпляр модификатора типа содержит модифицированный тип, который равен *T* , если `is_unsigned<T>` имеет значение true. В противном случае это наименьший тип со знаком `ST`, для которого `sizeof (T) <= sizeof (ST)`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
