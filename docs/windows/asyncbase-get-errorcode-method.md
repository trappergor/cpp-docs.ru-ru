---
title: "Метод AsyncBase::get_ErrorCode | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::get_ErrorCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_ErrorCode - метод"
ms.assetid: 50b4f8a2-9a21-4ea0-bb5d-7ff524d62aea
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод AsyncBase::get_ErrorCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает код ошибки для текущей асинхронной операции.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   get_ErrorCode  
)(HRESULT* errorCode) override;  
```  
  
#### Параметры  
 `errorCode`  
 Ячейка памяти, в которой хранится текущий код ошибки.  
  
## Возвращаемое значение  
 Значение S\_OK в случае успеха; в противном случае, если текущая асинхронная операция закрыта, значение E\_ILLEGAL\_METHOD\_CALL.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)