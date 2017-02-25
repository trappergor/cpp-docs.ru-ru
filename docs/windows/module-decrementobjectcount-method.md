---
title: "Метод Module::DecrementObjectCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::DecrementObjectCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DecrementObjectCount - метод"
ms.assetid: 6a06d1f9-7881-4f0e-891f-46b0e5c4f604
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Метод Module::DecrementObjectCount
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Уменьшает число объектов, отслеживаемых модулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual long DecrementObjectCount();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Счетчик, прежде чем операция уменьшения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
## <a name="see-also"></a>См. также раздел
[Класс модулей](../windows/module-class.md)