---
title: "Конструктор Module::Module | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Module, конструктор"
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Конструктор Module::Module
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует новый экземпляр класса Module.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Module();  
```  
  
## <a name="remarks"></a>Примечания  
 Этот конструктор является защищенным и не может быть вызван ключевым словом `new`. Вместо этого необходимо вызвать либо [метод Module::GetModule](../Topic/Module::GetModule%20Method.md) или [метод Module::Create](../windows/module-create-method.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс модулей](../windows/module-class.md)