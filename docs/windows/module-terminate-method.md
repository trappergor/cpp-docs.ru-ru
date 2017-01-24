---
title: "Метод Module::Terminate | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::Terminate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Terminate - метод"
ms.assetid: cf358117-45dc-43c7-ac1e-1e1eedc59e41
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод Module::Terminate
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приводит к завершению работы всех экземпляров фабрик, созданных модулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void Terminate();  
```  
  
## <a name="remarks"></a>Примечания  
 Освобождает фабрики в кэше.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс модулей](../windows/module-class.md)