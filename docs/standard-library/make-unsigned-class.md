---
title: Класс make_unsigned
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 42c722c5250a4989b930d8f1e6fe52f2eccc614a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413051"
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

Экземпляр модификатора типа содержит модифицированный тип, который является *T* Если `is_unsigned<T>` содержит значение true. В противном случае это наименьший тип со знаком `ST`, для которого `sizeof (T) <= sizeof (ST)`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
