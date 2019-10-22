---
title: Класс underlying_type
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: ea4768d78047112a7584ca49b0e4487fad55a970
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688845"
---
# <a name="underlying_type-class"></a>Класс underlying_type

Создает базовый целочисленный тип для типа перечисления.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Параметры

*T* \
Тип для изменения.

## <a name="remarks"></a>Заметки

@No__t_0 typedef элемента шаблона класса присваивает базовому целочисленному типу *t*, когда *t* — тип перечисления, в противном случае typedef не `type`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
