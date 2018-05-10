---
title: Класс is_trivially_constructible | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 757a5eb526bc8d4294a64cbdc9645e72285162ce
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="istriviallyconstructible-class"></a>Класс is_trivially_constructible

Проверяет, является ли тип просто создаваемым при использовании указанных типов аргументов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

`Args` Типы аргументов для сопоставления в конструктор `T`.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа имеет значение true, если тип `T` — просто создаваемый при использовании типов аргументов в `Args`, в противном случае — значение false. Тип `T` является просто создаваемым, если определение переменной `T t(std::declval<Args>()...);` имеет правильный формат и известно как не вызывающее нетривиальные операции. Как `T`, так и все типы в `Args` должны быть полными типами, `void`, либо массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
