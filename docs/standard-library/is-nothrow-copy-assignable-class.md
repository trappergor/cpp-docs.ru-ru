---
title: Класс is_nothrow_copy_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c5c5bdc1e944483071f0f1dcd53c3bc93eb6ed3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842941"
---
# <a name="isnothrowcopyassignable-class"></a>Класс is_nothrow_copy_assignable

Проверяет, имеет ли тип оператор назначения копии, который известен компилятору как не отбрасываемый.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа имеет значение true для типа с возможностью ссылки `T`, где `is_nothrow_assignable<T&, const T&>` имеет значение true, в противном случае — значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_nothrow_assignable](../standard-library/is-nothrow-assignable-class.md)<br/>
