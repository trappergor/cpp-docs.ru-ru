---
title: "Структура CriticalSectionTraits | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSectionTraits - структура"
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура CriticalSectionTraits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Специализирует объект CriticalSection для поддержки недопустимой критической секции или функции для освобождения критической секции.  
  
## Синтаксис  
  
```  
struct CriticalSectionTraits;  
```  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`Type`|`typedef`, задающий указатель на критическую секцию.  `Type` определяется как `typedef CRITICAL_SECTION* Type;`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод CriticalSectionTraits::GetInvalidValue](../windows/criticalsectiontraits-getinvalidvalue-method.md)|Специализирует шаблон CriticalSection так, что шаблон будет всегда являться недопустимым.|  
|[Метод CriticalSectionTraits::Unlock](../Topic/CriticalSectionTraits::Unlock%20Method.md)|Специализирует шаблон CriticalSection таким образом, чтобы он освободил владение указанным объектом критической секции.|  
  
## Иерархия наследования  
 `CriticalSectionTraits`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)