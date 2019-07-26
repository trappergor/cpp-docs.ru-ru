---
title: Класс is_trivially_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: 6f177463b985d3e7b2f7ab7783f9c3db0dcd5722
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448011"
---
# <a name="istriviallyconstructible-class"></a>Класс is_trivially_constructible

Проверяет, является ли тип просто создаваемым при использовании указанных типов аргументов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

*Args*\
Типы аргументов для сопоставления в конструкторе *T*.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является тривиально конструируемым с помощью типов аргументов в аргументах *args*, в противном случае — значение false. Тип *T* является тривиальным конструируемым, если определение `T t(std::declval<Args>()...);` переменной имеет правильный формат и известно, что он вызывает не нетривиальные операции. *T* и все типы в аргументах *args* должны быть полными типами, **void**или массивами неизвестной привязки.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
