---
title: Класс is_lvalue_reference | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_lvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecd065ff80b5c45bca863534e28bc467b3a4105c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105384"
---
# <a name="islvaluereference-class"></a>Класс is_lvalue_reference

Проверяет, является ли тип ссылкой lvalue.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр этого предиката типа содержит значение true, если тип *Ty* является ссылкой на объект или функцию, в противном случае он содержит значение false. Обратите внимание, что *Ty* не может быть ссылкой rvalue. Дополнительные сведения о rvalues см. в разделе [Оператор объявления ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Значения Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
