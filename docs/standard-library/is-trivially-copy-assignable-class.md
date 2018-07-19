---
title: Класс is_trivially_copy_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f7c4c748d7328f534aebfb2133c72635bbdc36f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953970"
---
# <a name="istriviallycopyassignable-class"></a>Класс is_trivially_copy_assignable

Проверяет, есть ли у типа тривиальный оператор присваивания копии.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Параметры

*T* запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является классом, имеющим тривиальный оператор присваивания копии, в противном случае он содержит значение false.

Конструктор присваивания для класса *T* является тривиальным, если он предоставляется неявно, класс *T* не имеет виртуальных функций, класс *T* не имеет виртуальных баз, классы все нестатические данные-члены типа класса имеют тривиальные операторы присваивания и классы всех нестатических членов массива типов класса имеют тривиальные операторы присваивания.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
