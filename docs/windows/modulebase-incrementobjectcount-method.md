---
title: Метод ModuleBase::IncrementObjectCount | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- IncrementObjectCount method
ms.assetid: 2d70b472-684c-4bb7-8bab-09505cfcaf28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b0e0fd6ecfd4d30dd4921c99d873c23b533ee24
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875478"
---
# <a name="modulebaseincrementobjectcount-method"></a>Метод ModuleBase::IncrementObjectCount
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual long IncrementObjectCount() = 0;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Счетчик перед выполнением операции инкремента.  
  
## <a name="remarks"></a>Примечания  
 При реализации увеличивает число объектов, отслеживаемых модулем.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [ModuleBase-класс](../windows/modulebase-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)