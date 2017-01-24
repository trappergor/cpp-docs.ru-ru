---
title: "Метод AsyncBase::TryTransitionToError | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::TryTransitionToError"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryTransitionToError - метод"
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод AsyncBase::TryTransitionToError
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, может ли указанный код ошибки изменить состояние внутренней ошибки.  
  
## Синтаксис  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### Параметры  
 `error`  
 Ошибка HRESULT.  
  
## Возвращаемое значение  
 `true`, если состояние внутренней ошибки было изменено; в противном случае `false`.  
  
## Примечания  
 Эта операция изменяет состояние ошибки только если состояние ошибки уже имеет значение S\_OK.  Эта операция не срабатывает, если состояние ошибки уже ошибка, отменено, выполнено или закрыто.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)