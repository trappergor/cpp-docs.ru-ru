---
title: "CancelTransitionPolicy - перечисление | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CancelTransitionPolicy - перечисление"
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CancelTransitionPolicy - перечисление
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Показывает, как попытка перехода асинхронной операции к окончательному состоянию завершения или ошибки должна происходить с учетом запрошенного клиентом состояния отмены.  
  
## Синтаксис  
  
```  
enum CancelTransitionPolicy;  
```  
  
## Члены  
  
### Значения  
  
|Имя|Описание|  
|---------|--------------|  
|`RemainCanceled`|Если асинхронная операция в данный момент находится в запрошенном клиентом состоянии отмены, то это означает, что этот элемент остается в отмененном состоянии, в отличие от перехода к конечным состояниям завершения или ошибки.|  
|`TransitionFromCanceled`|Если асинхронная операция в данный момент находится в запрошенном клиентом состоянии отмены, то это означает, что состояние должно перейти из этого состояния отмены в конечное состояние завершения или ошибки, как определяется вызовом, который использует этот флажок.|  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)