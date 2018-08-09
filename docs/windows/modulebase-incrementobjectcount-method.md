---
title: Метод ModuleBase::IncrementObjectCount | Документация Майкрософт
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
ms.openlocfilehash: 1ee6c71ba6de195386cda78f2e44902c43523143
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011079"
---
# <a name="modulebaseincrementobjectcount-method"></a>Метод ModuleBase::IncrementObjectCount
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 [Класс ModuleBase](../windows/modulebase-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)