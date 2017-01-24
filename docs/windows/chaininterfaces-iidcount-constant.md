---
title: "Константа ChainInterfaces::IidCount | Microsoft Docs"
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
  - "implements/Microsoft::WRL::ChainInterfaces::IidCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IidCount - константа"
ms.assetid: d4a90aa0-513c-4e99-b978-e12149734936
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Константа ChainInterfaces::IidCount
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Общее число идентификаторов интерфейса, содержащихся в интерфейсах, указанных параметрами `I0` шаблона через `I9`.  
  
## Синтаксис  
  
```  
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;  
```  
  
## Возвращаемое значение  
 Общее число идентификаторов интерфейса.  
  
## Примечания  
 Параметры шаблона `I0` и `I1` и параметры `I2` через `I9` являются необязательными. Количество IID каждого интерфейса обычно равно одному.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Структура ChainInterfaces](../windows/chaininterfaces-structure.md)