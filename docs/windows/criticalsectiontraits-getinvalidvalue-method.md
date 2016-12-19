---
title: "Метод CriticalSectionTraits::GetInvalidValue | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInvalidValue - метод"
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод CriticalSectionTraits::GetInvalidValue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Специализирует шаблон CriticalSection так, что шаблон будет всегда являться недопустимым.  
  
## Синтаксис  
  
```  
inline static Type GetInvalidValue();  
```  
  
## Возвращаемое значение  
 Всегда возвращает указатель на недопустимую критическую секцию.  
  
## Примечания  
 Модификатор *Type* определен как `typedef CRITICAL_SECTION* Type;`.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)