---
title: Метод CompareStringOrdinal | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs:
- C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 952de0ca136d29eb0b170856410b18a1d65120c1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612892"
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

*lhs*  
Первый HSTRING для сравнения.

*правая часть*  
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

[Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)