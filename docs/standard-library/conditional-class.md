---
title: Класс conditional | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d51397080267dd50f012b274e95ac4c9aa4fa64
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="conditional-class"></a>Класс conditional

Выделяет один из 2 типов в зависимости от указанного условия.

## <a name="syntax"></a>Синтаксис

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>Параметры

`B` Значение, определяющее выбранный тип.

`T1` Результат типа, если B — true.

`T2` Результат типа, если B — false.

## <a name="remarks"></a>Примечания

Член шаблона typedef `conditional<B, T1, T2>::type` равен `T1` , если параметр `B` равен `true`, или `T2` , если параметр `B` равен `false`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
