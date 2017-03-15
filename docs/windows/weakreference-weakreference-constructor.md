---
title: "Конструктор WeakReference::WeakReference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::WeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakReference, конструктор"
ms.assetid: 4959a9d7-78ea-423d-a46b-50d010d29fff
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Конструктор WeakReference::WeakReference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WeakReference();  
```  
  
## <a name="remarks"></a>Примечания  
 Инициализирует новый экземпляр [класс WeakReference](../windows/weakreference-class1.md).  
  
 Указатель сильную ссылку для объекта, WeakReference инициализируется `nullptr`, и надежный счетчик устанавливается равным 1.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
    
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)