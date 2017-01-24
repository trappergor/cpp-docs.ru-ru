---
title: "Оператор HStringReference::Operator= | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator="
dev_langs: 
  - "C++"
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор HStringReference::Operator=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Перемещает значение другого объекта HStringReference в текущий объект HStringReference.  
  
## Синтаксис  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### Параметры  
 `other`  
 Существующий объект HStringReference.  
  
## Примечания  
 Значение существующего объекта `other` копируется в текущий объект HStringReference, а затем объект `other` удаляется.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)