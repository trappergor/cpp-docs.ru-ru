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
ms.openlocfilehash: 58e808510868e375672ee5de0b27c4bed3c568e0
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464055"
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