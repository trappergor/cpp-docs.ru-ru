---
title: "Функция GetModuleBase | Microsoft Docs"
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
  - "implements/Microsoft::WRL::GetModuleBase"
dev_langs: 
  - "C++"
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция GetModuleBase
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает указатель [ModuleBase](../windows/modulebase-class.md), позволяющий увеличивать и уменьшать счетчик ссылок объекта [RuntimeClass](../windows/runtimeclass-class.md).  
  
## Синтаксис  
  
```cpp  
inline Details::ModuleBase* GetModuleBase() throw()  
```  
  
## Возвращаемое значение  
 Указатель на объект `ModuleBase`.  
  
## Заметки  
 Эта функция используется внутренне для увеличения и уменьшения числа ссылок объектов.  
  
 Эту функцию можно использовать для управления счетчиками ссылок путем вызова [ModuleBase::IncrementObjectCount](../windows/modulebase-incrementobjectcount-method.md) и [ModuleBase::DecrementObjectCount](../Topic/ModuleBase::DecrementObjectCount%20Method.md).  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)