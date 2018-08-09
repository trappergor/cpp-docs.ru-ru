---
title: Метод WeakReference::DecrementStrongReference | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c7e2161c5451fe82e12918f00e8cb2cde37d336
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642319"
---
# <a name="weakreferencedecrementstrongreference-method"></a>Метод WeakReference::DecrementStrongReference
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ULONG DecrementStrongReference();  
```  
  
## <a name="remarks"></a>Примечания  
 Уменьшает текущий счетчик строгая ссылка **WeakReference** объекта.  
  
 Надежный счетчик достигает нуля, строгая ссылка имеет значение **nullptr**.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Счетчик уменьшается на единицу строгую ссылку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Класс WeakReference](../windows/weakreference-class1.md)  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)