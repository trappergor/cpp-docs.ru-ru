---
title: "Метод WeakReference::DecrementStrongReference | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs: C++
helpviewer_keywords: DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8526385764206b3bb72691fa0ed5232f8f6edf8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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