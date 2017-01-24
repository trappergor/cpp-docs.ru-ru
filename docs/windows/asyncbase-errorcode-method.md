---
title: "Метод AsyncBase::ErrorCode | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::ErrorCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorCode - метод"
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод AsyncBase::ErrorCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает код ошибки для текущей асинхронной операции.  
  
## Синтаксис  
  
```  
inline void ErrorCode(  
   HRESULT *error  
);  
```  
  
#### Параметры  
 `error`  
 Расположение, в котором эта операция сохраняет текущий код ошибки.  
  
## Примечания  
 Данная операция является потокобезопасной.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)