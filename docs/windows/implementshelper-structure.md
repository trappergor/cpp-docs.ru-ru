---
title: "Структура ImplementsHelper | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::ImplementsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ImplementsHelper - структура"
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Структура ImplementsHelper
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### Параметры  
 `RuntimeClassFlagsT`  
 Поле флагов, которое определяет один или несколько перечислителей [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
 `ILst`  
 Список идентификаторов интерфейсов.  
  
 `IsDelegateToClass`  
 Укажите `true`, если текущий экземпляр Implements является базовым классом первого идентификатора интерфейса в `ILst`; в противном случае `false`.  
  
## Примечания  
 Помогает реализовать структуру [Implements](../Topic/Implements%20Structure.md).  
  
 Этот шаблон проходит список интерфейсов и добавляет их в качестве базовых классов и информации, необходимой для включения QueryInterface.  
  
## Члены  
  
## Иерархия наследования  
 `ImplementsHelper`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/ru-ru/00000000-0000-0000-0000-000000000000)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)