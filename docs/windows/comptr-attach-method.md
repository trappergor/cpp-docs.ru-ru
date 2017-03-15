---
title: "Метод ComPtr::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach - метод"
ms.assetid: 5b911f2d-9830-4dc7-b9e3-527abd55d2c8
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод ComPtr::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Связывает этот ComPtr с типом интерфейса, указанным текущим параметром типа шаблона.  
  
## Синтаксис  
  
```  
void Attach(  
   _In_opt_ InterfaceType* other  
);  
```  
  
#### Параметры  
 `other`  
 Тип интерфейса.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)