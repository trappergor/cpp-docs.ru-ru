---
title: "Метод AsyncBase::CheckValidStateForDelegateCall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckValidStateForDelegateCall - метод"
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод AsyncBase::CheckValidStateForDelegateCall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, можно ли изменить свойства делегата в текущем асинхронном состоянии.  
  
## Синтаксис  
  
```  
inline HRESULT CheckValidStateForDelegateCall();  
```  
  
## Возвращаемое значение  
 S\_OK, если свойства делегата можно изменить; в противном случае — E\_ILLEGAL\_METHOD\_CALL.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)