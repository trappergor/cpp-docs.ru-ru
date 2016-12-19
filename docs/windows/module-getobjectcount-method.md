---
title: "Метод Module::GetObjectCount | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GetObjectCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetObjectCount - метод"
ms.assetid: 9fe29747-7e7f-40f2-9f6b-9a206b17fa8e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод Module::GetObjectCount
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает количество объектов, управляемых этим модулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual long GetObjectCount() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Текущее количество объектов, управляемых этим модулем.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс модулей](../windows/module-class.md)