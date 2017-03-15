---
title: "Метод ComPtr::Swap | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::Swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Swap - метод"
ms.assetid: 74275f00-b24e-4b4c-b8b6-ac2aa2dd7ae9
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод ComPtr::Swap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Меняет местами интерфейс, управляемый текущим ComPtr с интерфейсом, управляемым указанным ComPtr.  
  
## Синтаксис  
  
```  
void Swap(  
   _Inout_ ComPtr&& r  
);  
  
void Swap(  
   _Inout_ ComPtr& r  
);  
```  
  
#### Параметры  
 `r`  
 ComPtr.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)