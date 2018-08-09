---
title: Метод WeakReference::IncrementStrongReference | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- IncrementStrongReference method
ms.assetid: d0232426-a8cb-48b4-99d4-165de2d66cb9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 764a47fe03a2ad9f4e4d3d64a5627acc9c72d1b5
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018875"
---
# <a name="weakreferenceincrementstrongreference-method"></a>Метод WeakReference::IncrementStrongReference
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
ULONG IncrementStrongReference();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Счетчик увеличивается строгую ссылку.  
  
## <a name="remarks"></a>Примечания  
 Увеличивает счетчик строгую ссылку текущего **WeakReference** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Класс WeakReference](../windows/weakreference-class1.md)  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)