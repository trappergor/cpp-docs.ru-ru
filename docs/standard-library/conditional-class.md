---
title: Класс conditional
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: b8f0f69cc1e4f6966bc9ccb63fe529436295badd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457324"
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

*&* \
Значение, определяющее выбранный тип.

*T1*\
Результат типа, если B — true.

*T2*\
Результат типа, если B — false.

## <a name="remarks"></a>Примечания

Typedef `conditional<B, T1, T2>::type` элемента шаблона оценивается как *T1* , если *b* возвращает **значение true**, а значение *T2* равно, если *b* возвращает **false**.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
