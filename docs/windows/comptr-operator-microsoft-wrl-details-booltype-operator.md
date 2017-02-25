---
title: "Оператор ComPtr::operator Microsoft::WRL::Details::BoolType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Оператор ComPtr::operator Microsoft::WRL::Details::BoolType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, управляет ли ComPtr временем существования объекта интерфейса.  
  
## Синтаксис  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## Возвращаемое значение  
 Если интерфейс связан с этим ComPtr, адрес данных\-члена [BoolStruct::Member](../Topic/BoolStruct::Member%20Data%20Member.md); в противном случае `nullptr`.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)   
 [Метод ComPtr::Get](../windows/comptr-get-method.md)