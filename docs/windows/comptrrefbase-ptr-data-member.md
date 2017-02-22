---
title: "Элемент данных ComPtrRefBase::ptr_ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRefBase::ptr_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr_ - элемент данных"
ms.assetid: 9b1c07f9-531f-41c2-9ac0-f7cf49f5f586
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Элемент данных ComPtrRefBase::ptr_
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
T* ptr_;  
```  
  
## Заметки  
 Указатель на тип, указанный в текущем параметре шаблона.  
  
## Примечания  
 `ptr_` является защищенными данными\-членом.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Класс ComPtrRefBase](../windows/comptrrefbase-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)