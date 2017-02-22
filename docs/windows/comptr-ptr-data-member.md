---
title: "Элемент данных ComPtr::ptr_ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::ptr_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr_ - элемент данных"
ms.assetid: c84f9dda-8ff9-422d-91f2-1a41206bf9ad
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Элемент данных ComPtr::ptr_
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Содержит указатель на интерфейс, который связан и управляется текущим ComPtr.  
  
## Синтаксис  
  
```  
InterfaceType *ptr_;  
```  
  
## Примечания  
 `ptr_` защищенный внутренний элемент данных.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)