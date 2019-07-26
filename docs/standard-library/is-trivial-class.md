---
title: Класс is_trivial
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivial
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
ms.openlocfilehash: 1d218848fd65ca68022e3e66df02201582626711
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457423"
---
# <a name="istrivial-class"></a>Класс is_trivial

Проверяет, является ли тип тривиальным.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является тривиальным типом, в противном случае — значение false. К тривиальным типам относятся скалярные типы, типы тривиально копируемых классов, массивы этих типов и версии типов с квалификатором cv.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
