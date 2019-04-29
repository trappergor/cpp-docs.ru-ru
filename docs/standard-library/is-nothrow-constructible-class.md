---
title: Класс is_nothrow_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_constructible
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
ms.openlocfilehash: 9ea11d54d49bf8f6ae6416f9663c2593cc66ea3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383611"
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
