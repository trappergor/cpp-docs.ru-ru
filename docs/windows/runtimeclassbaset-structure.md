---
title: "Структура RuntimeClassBaseT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT"
dev_langs: 
  - "C++"
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Структура RuntimeClassBaseT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
#### Параметры  
 `RuntimeClassTypeT`  
 Поле флагов, которое определяет один или несколько перечислителей [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Заметки  
 Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.  
  
## Члены  
  
## Иерархия наследования  
 `RuntimeClassBaseT`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/ru-ru/00000000-0000-0000-0000-000000000000)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)