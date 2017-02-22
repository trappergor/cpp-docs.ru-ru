---
title: "Структура InterfaceList | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceList - структура"
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Структура InterfaceList
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template <  
   typename T,  
   typename U  
>  
struct InterfaceList;  
```  
  
#### Параметры  
 `T`  
 Имя интерфейса; первый интерфейс в рекурсивном списке.  
  
 `U`  
 Имя интерфейса; оставшиеся интерфейсы в рекурсивном списке.  
  
## Заметки  
 Используется для создания рекурсивного списка интерфейсов.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`FirstT`|Синоним для параметра `T` шаблона.|  
|`RestT`|Синоним для параметра `U` шаблона.|  
  
## Иерархия наследования  
 `InterfaceList`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)