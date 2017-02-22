---
title: "Метод WeakReference::IncrementStrongReference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IncrementStrongReference - метод"
ms.assetid: d0232426-a8cb-48b4-99d4-165de2d66cb9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Метод WeakReference::IncrementStrongReference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ULONG IncrementStrongReference();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Счетчик увеличивается строгой ссылки.  
  
## <a name="remarks"></a>Примечания  
 Увеличивает значение счетчика строгой ссылки объекта WeakReference.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также раздел  
[Класс WeakReference](../windows/weakreference-class1.md)  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)