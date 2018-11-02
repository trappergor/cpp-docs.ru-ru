---
title: Класс conditional
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: be81a1bc32f2f86f1d79970868933bddb8dc3620
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523023"
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

*B*<br/>
Значение, определяющее выбранный тип.

*T1*<br/>
Результат типа, если B — true.

*T2*<br/>
Результат типа, если B — false.

## <a name="remarks"></a>Примечания

Член шаблона typedef `conditional<B, T1, T2>::type` принимает значение *T1* при *B* принимает значение **true**и дает в результате *T2* при  *B* принимает значение **false**.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
