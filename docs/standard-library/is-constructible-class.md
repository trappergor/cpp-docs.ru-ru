---
title: Класс is_constructible | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2461d7986e87bed846d09d6e3938a339237c8f8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845171"
---
# <a name="isconstructible-class"></a>Класс is_constructible

Проверяет, является ли тип конструируемым при использовании указанных типов аргументов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

`Args` Типы аргументов для сопоставления в конструктор `T`.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа имеет значение true, если тип `T` — конструируемый при использовании типов аргументов в `Args`, в противном случае — значение false. Тип `T` — конструируемый, если определение переменной `T t(std::declval<Args>()...);` имеет правильный формат. Как `T`, так и все типы в `Args`, должны быть полными типами, `void` либо массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
