---
title: Метод CompareStringOrdinal | Документы Microsoft
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
ms.openlocfilehash: e3abf87340671d1ac4851b055a57896e340d0c20
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="comparestringordinal-method"></a>Метод CompareStringOrdinal
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
#### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый HSTRING для сравнения.  
  
 `rhs`  
 Второй HSTRING для сравнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|Значение|Условие|  
|-----------|---------------|  
|-1|Значение `lhs` меньше `rhs`.|  
|0|`lhs` равняется `rhs`.|  
|1|Значение `lhs` больше значения `rhs`.|  
  
## <a name="remarks"></a>Примечания  
 Сравнивает два указанных объекта HSTRING и возвращает целое число, которое показывает их относительное положение в порядке сортировки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)