---
title: "Метод RuntimeClass::GetIids | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::GetIids"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetIids - метод"
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод RuntimeClass::GetIids
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает массив, содержащий идентификаторы интерфейса, реализованные текущим объектом RuntimeClass.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### Параметры  
 `iidCount`  
 Когда эта операция будет завершена, общее число элементов в массиве `iids`.  
  
 `iids`  
 Когда эта операция будет завершена, указатель на массив идентификаторов интерфейса.  
  
## Возвращаемое значение  
 S\_OK, если операция завершилась удачно; в противном случае E\_OUTOFMEMORY.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)