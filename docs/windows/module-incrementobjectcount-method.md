---
title: "Метод Module::IncrementObjectCount | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::IncrementObjectCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IncrementObjectCount - метод"
ms.assetid: 268b79be-15c3-4b07-884e-18da2c7281f2
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод Module::IncrementObjectCount
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Увеличивает число объектов, отслеживаемых модулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual long IncrementObjectCount();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Счетчик перед выполнением операции инкремента.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс модулей](../windows/module-class.md)