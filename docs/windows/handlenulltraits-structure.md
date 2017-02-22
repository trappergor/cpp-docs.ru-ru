---
title: "Структура HANDLENullTraits | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HANDLENullTraits - структура"
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Структура HANDLENullTraits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет общие характеристики неинициализированного дескриптора.  
  
## Синтаксис  
  
```  
struct HANDLENullTraits;  
```  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`Type`|Синоним для HANDLE.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод HANDLENullTraits::Close](../windows/handlenulltraits-close-method.md)|Закрывает указанный дескриптор.|  
|[Метод HANDLENullTraits::GetInvalidValue](../windows/handlenulltraits-getinvalidvalue-method.md)|Представляет недопустимый дескриптор.|  
  
## Иерархия наследования  
 `HANDLENullTraits`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)