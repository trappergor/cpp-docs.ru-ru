---
title: "Структура BoolStruct | Microsoft Docs"
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
  - "internal/Microsoft::WRL::Details::BoolStruct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BoolStruct - структура"
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура BoolStruct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
struct BoolStruct;  
```  
  
## Заметки  
 Структура BoolStruct определяет, управляет ли ComPtr временем существования объекта интерфейса.  BoolStruct используется внутренне оператором [BoolType\(\)](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md).  
  
## Члены  
  
### Открытые члены данных  
  
|Name|Описание|  
|----------|--------------|  
|[Элемент данных BoolStruct::Member](../Topic/BoolStruct::Member%20Data%20Member.md)|Указывает, что [ComPtr](../windows/comptr-class.md) управляет или не управляет временем существования объекта интерфейса.|  
  
## Иерархия наследования  
 `BoolStruct`  
  
## Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)   
 [Оператор ComPtr::operator Microsoft::WRL::Details::BoolType](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)