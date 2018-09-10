---
title: Класс is_nothrow_move_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_move_assignable
ms.assetid: 000baa02-cbba-49de-9870-af730033348e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86a37ce88870ff2c60ed4f0a693bdaae32523c24
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108242"
---
# <a name="isnothrowmoveassignable-class"></a>Класс is_nothrow_move_assignable

Проверяет, имеет ли тип оператор присваивания перемещения **nothrow**.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* имеет nothrow перемещения оператора назначения, в противном случае он содержит значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
