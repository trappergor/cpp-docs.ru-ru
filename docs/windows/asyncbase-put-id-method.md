---
title: "Метод AsyncBase::put_Id | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::put_Id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "put_Id - метод"
ms.assetid: aebad85f-4774-42de-b625-a9cf5f65cb4e
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод AsyncBase::put_Id
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Устанавливает дескриптор асинхронной операции.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   put_Id  
)(const unsigned int id);  
```  
  
#### Параметры  
 `id`  
 Ненулевой дескриптор.  
  
## Возвращаемое значение  
 S\_OK, если операция завершилась удачно; в противном случае — значение E\_INVALIDARG или E\_ILLEGAL\_METHOD\_CALL.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)