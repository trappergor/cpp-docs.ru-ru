---
title: "Метод ChainInterfaces::CastToUnknown | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown - метод"
ms.assetid: a6a58555-e5b0-4773-aba0-959d9d362c6b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод ChainInterfaces::CastToUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приводит указатель интерфейса типа, указанного в параметре шаблона `I0` к указателю на интерфейс IUnknown.  
  
## Синтаксис  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## Возвращаемое значение  
 Указатель на IUnknown.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Структура ChainInterfaces](../windows/chaininterfaces-structure.md)