---
title: "Структура ArgTraitsHelper | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::ArgTraitsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraitsHelper - структура"
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Структура ArgTraitsHelper
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template<  
   typename TDelegateInterface  
>  
struct ArgTraitsHelper;  
```  
  
#### Параметры  
 `TDelegateInterface`  
 Интерфейс делегата.  
  
## Заметки  
 Помогает определить общие характеристики аргументов делегата.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`methodType`|Синоним для `decltype(&TDelegateInterface::Invoke)`.|  
|`Traits`|Синоним для `ArgTraits<methodType>`.|  
  
### Открытые константы  
  
|Имя|Описание|  
|---------|--------------|  
|[Константа ArgTraitsHelper::args](../windows/argtraitshelper-args-constant.md)|Помогает [ArgTraits::args](../windows/argtraits-args-constant.md) продолжать подсчет количества параметров в методе Invoke интерфейса делегата.|  
  
## Иерархия наследования  
 `ArgTraitsHelper`  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)