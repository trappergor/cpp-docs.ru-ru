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
ms.openlocfilehash: f94390b96770a84b35de67f4d3a38644132d8ce8
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107447"
---
# <a name="isconstructible-class"></a>Класс is_constructible

Проверяет, является ли тип конструируемым при использовании указанных типов аргументов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

*Args*<br/>
Типы аргументов для сопоставления в конструктор *T*.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* — конструируемый при использовании типов аргументов в *Args*, в противном случае он содержит значение false. Тип *T* конструируемым Если определение переменной `T t(std::declval<Args>()...);` имеет правильный формат. Оба *T* и все типы в *Args* должны быть полными типами **void**, или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
