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
ms.openlocfilehash: 688252b4b361357f4dba862574ce6698d61b7c86
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102763"
---
# <a name="istriviallycopyassignable-class"></a>Класс is_trivially_copy_assignable

Проверяет, есть ли у типа тривиальный оператор присваивания копии.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является классом, имеющим тривиальный оператор присваивания копии, в противном случае он содержит значение false.

Конструктор присваивания для класса *T* является тривиальным, если он предоставляется неявно, класс *T* не имеет виртуальных функций, класс *T* не имеет виртуальных баз, классы все нестатические данные-члены типа класса имеют тривиальные операторы присваивания и классы всех нестатических членов массива типов класса имеют тривиальные операторы присваивания.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
