---
title: "Константа ArgTraitsHelper::args | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::ArgTraitsHelper::args"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "args - константа"
ms.assetid: 1c0efa32-c072-43e3-bbd9-a3f6aec069a2
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Константа ArgTraitsHelper::args
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
static const int args = Traits::args;  
```  
  
## Заметки  
 Помогает [ArgTraitsHelper::args](../windows/argtraitshelper-args-constant.md) продолжать подсчет количества параметров в методе Invoke интерфейса делегата.  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Структура ArgTraitsHelper](../windows/argtraitshelper-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)