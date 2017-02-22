---
title: "Метод RuntimeClass::InternalAddRef | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::InternalAddRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InternalAddRef - метод"
ms.assetid: b8ed7f93-83d8-47ec-988c-98fe65104e7a
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод RuntimeClass::InternalAddRef
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Увеличивает значение счетчика ссылок для текущего объекта RuntimeClass.  
  
## Синтаксис  
  
```  
ULONG InternalAddRef();  
```  
  
## Возвращаемое значение  
 Результирующее значение счетчика ссылок.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)