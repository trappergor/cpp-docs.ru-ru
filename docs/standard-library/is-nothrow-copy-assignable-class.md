---
title: Класс is_nothrow_copy_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47cfa4d49dce7f7503c9e707d3a2f8787b4f53a3
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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
