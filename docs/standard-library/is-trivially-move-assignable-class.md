---
title: Класс is_trivially_move_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19346075d0b52be7820adfe60e77e0f76113bc98
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44099913"
---
# <a name="istriviallymoveassignable-class"></a>Класс is_trivially_move_assignable

Проверяет, есть ли у типа тривиальный оператор присваивания перемещением.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом, имеющим тривиальный оператор присваивания перемещения, в противном случае он содержит значение false.

Оператор присваивания перемещения для класса *Ty* является тривиальным если:

он неявно предоставляется;

Класс *Ty* не имеет виртуальных функций

Класс *Ty* не имеет виртуальных баз

классы всех нестатических элементов данных типа класса имеют тривиальные операторы присваивания перемещением;

классы всех нестатических элементов данных массива типов класса имеют тривиальные операторы присваивания перемещением.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
