---
title: "Метод WeakReference::DecrementStrongReference | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bda6de03ce17db7ebac751865686c3e74a26d0d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="weakreferencedecrementstrongreference-method"></a>Метод WeakReference::DecrementStrongReference
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ULONG DecrementStrongReference();  
```  
  
## <a name="remarks"></a>Примечания  
 Уменьшает счетчик строгого ссылок объекта WeakReference.  
  
 Если строгую ссылку счетчик становится равным нулю, строгая ссылка имеет значение `nullptr`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Счетчик уменьшается на единицу строгую ссылку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
[Класс WeakReference](../windows/weakreference-class1.md)  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)