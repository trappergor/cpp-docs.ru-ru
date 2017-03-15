---
title: "Метод Implements::CastToUnknown | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown - метод"
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод Implements::CastToUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает указатель на базовый интерфейс IUnknown.  
  
## Синтаксис  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## Возвращаемое значение  
 Эта операция всегда успешна и возвращает указатель IUnknown.  
  
## Примечания  
 Внутренняя вспомогательная функция.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Структура Implements](../Topic/Implements%20Structure.md)