---
title: "Структура HANDLETraits | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HANDLETraits - структура"
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура HANDLETraits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет общие характеристики дескриптора.  
  
## Синтаксис  
  
```  
struct HANDLETraits;  
```  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`Type`|Синоним для HANDLE.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод HANDLETraits::Close](../windows/handletraits-close-method.md)|Закрывает указанный дескриптор.|  
|[Метод HANDLETraits::GetInvalidValue](../Topic/HANDLETraits::GetInvalidValue%20Method.md)|Представляет недопустимый дескриптор.|  
  
## Иерархия наследования  
 `HANDLETraits`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)