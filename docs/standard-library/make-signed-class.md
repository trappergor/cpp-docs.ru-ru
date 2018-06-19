---
title: Класс make_signed | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::make_signed
dev_langs:
- C++
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b58c31c7f4180f9c65b04bbb852bf15c7315c35d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859372"
---
# <a name="makesigned-class"></a>Класс make_signed

Создает тип или наименьшей знаковый тип, размер которого больше или равен размеру типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>Параметры

`T` Тип для изменения.

## <a name="remarks"></a>Примечания

Экземпляр модификатора типа содержит модифицированный тип, т. е. `T`, если `is_signed<T>` содержит значение true. В противном случае это наименьший тип без знака `UT` для которого `sizeof (T) <= sizeof (UT)`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
