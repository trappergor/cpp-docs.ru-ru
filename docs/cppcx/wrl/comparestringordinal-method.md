---
title: Метод CompareStringOrdinal
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: c9dbbe8926036ea18210fb30928fafc40093092e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785249"
---
# <a name="comparestringordinal-method"></a>Метод CompareStringOrdinal

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
inline INT32 CompareStringOrdinal(
   HSTRING lhs,
   HSTRING rhs)
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый HSTRING для сравнения.

*правая часть*<br/>
Второй HSTRING для сравнения.

## <a name="return-value"></a>Возвращаемое значение

|Значение|Условие|
|-----------|---------------|
|-1|*LHS* — меньше, чем *rhs*.|
|0|*LHS* равно *rhs*.|
|1|*LHS* больше, чем *rhs*.|

## <a name="remarks"></a>Примечания

Сравнивает два указанных объекта HSTRING и возвращает целое число, которое показывает их относительное положение в порядке сортировки.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers::Details](microsoft-wrl-wrappers-details-namespace.md)