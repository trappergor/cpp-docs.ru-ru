---
title: Класс is_nothrow_constructible | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0726839baadf5265d604f231615f1add069ccfcb
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106534"
---
# <a name="isnothrowconstructible-class"></a>Класс is_nothrow_constructible

Проверяет, является ли тип конструируемым и известным как не выдающим исключения при использовании указанных типов аргументов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

*Args*<br/>
Типы аргументов для сопоставления в конструктор *T*.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* — конструируемый при использовании типов аргументов в *Args*и конструктор известен, компилятор не будет выдавать; в противном случае он содержит значение false. Тип *T* конструируемым Если определение переменной `T t(std::declval<Args>()...);` имеет правильный формат. Оба *T* и все типы в *Args* должны быть полными типами **void**, или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
