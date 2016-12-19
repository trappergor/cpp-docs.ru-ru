---
title: "Метод AsyncBase::Close | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close - метод"
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод AsyncBase::Close
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Закрывает асинхронную операцию.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## Возвращаемое значение  
 S\_OK, если операция закрывается или уже закрыта; в противном случае E\_ILLEGAL\_STATE\_CHANGE.  
  
## Примечания  
 Close\(\) является реализацией по умолчанию для IAsyncInfo::Close и фактически не делает ничего.  Для фактического закрытия асинхронной операции переопределите чисто виртуальный метод OnClose\(\).  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)