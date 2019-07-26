---
title: Класс is_lvalue_reference
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_lvalue_reference
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
ms.openlocfilehash: 5bcd5c8333f011475cb11a452759c8986ab22215
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456207"
---
# <a name="islvaluereference-class"></a>Класс is_lvalue_reference

Проверяет, является ли тип ссылкой lvalue.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр этого предиката типа содержит значение true, если тип *Ty* является ссылкой на объект или функцию, в противном случае — значение false. Обратите внимание, что *Ty* не может быть ссылкой rvalue. Дополнительные сведения о rvalues см. в разделе [Оператор объявления ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[Значения Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)
