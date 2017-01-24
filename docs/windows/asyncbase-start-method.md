---
title: "Метод AsyncBase::Start | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start - метод"
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод AsyncBase::Start
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Запускает асинхронную операцию.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## Возвращаемое значение  
 S\_OK, если операция запускается или уже запущена; в противном случае E\_ILLEGAL\_STATE\_CHANGE.  
  
## Примечания  
 Start\(\) является реализацией по умолчанию для IAsyncInfo::Start и не выполняет никакой работы.  Для фактического запуска асинхронной операции следует переопределить чисто виртуальный метод OnStart\(\).  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)