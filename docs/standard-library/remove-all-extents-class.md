---
title: Класс remove_all_extents | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_all_extents
dev_langs:
- C++
helpviewer_keywords:
- remove_all_extents class
- remove_all_extents
ms.assetid: 548dc536-82e7-423a-b8c1-443d66d9632e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18332f0c5d452c04079ff68bebbbdae19c4ed0d5
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953883"
---
# <a name="removeallextents-class"></a>Класс remove_all_extents

Создает из типа массива тип, не относящийся к массиву.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct remove_all_extents;

template <class T>
using remove_all_extents_t = typename remove_all_extents<T>::type;
```

### <a name="parameters"></a>Параметры

*T* введите для изменения.

## <a name="remarks"></a>Примечания

Экземпляр `remove_all_extents<T>` содержит модифицированный тип, который является типом элемента типа массива *T* с все измерения массива удалены, или *T* Если *T* не является типом массива.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "remove_all_extents<int> == "
        << typeid(std::remove_all_extents_t<int>).name()
        << std::endl;
    std::cout << "remove_all_extents_t<int[5]> == "
        << typeid(std::remove_all_extents_t<int[5]>).name()
        << std::endl;
    std::cout << "remove_all_extents_t<int[5][10]> == "
        << typeid(std::remove_all_extents_t<int[5][10]>).name()
        << std::endl;

    return (0);
    }
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс remove_extent](../standard-library/remove-extent-class.md)<br/>
